# Workflows n8n - MyBestEvents (Exports Importables)

Ce document contient les structures JSON pour configurer votre automatisation d'acquisition et de conversion de partenaires.

## 🔎 WF1 — Acquisition Google Places
Ce workflow tourne chaque matin pour trouver de nouveaux partenaires en Occitanie.

```json
{
  "name": "WF1_ACQUISITION_GOOGLE_PLACES",
  "nodes": [
    {
      "name": "Cron",
      "type": "n8n-nodes-base.cron",
      "parameters": {
        "triggerTimes": [{ "hour": 8, "minute": 0 }]
      }
    },
    {
      "name": "Google Places Search",
      "type": "n8n-nodes-base.httpRequest",
      "parameters": {
        "url": "https://maps.googleapis.com/maps/api/place/textsearch/json",
        "queryParameters": {
          "query": "yoga OR coach sportif OR spa OR bien-être Occitanie",
          "key": "YOUR_API_KEY"
        }
      }
    },
    {
      "name": "Format Data",
      "type": "n8n-nodes-base.function",
      "parameters": {
        "functionCode": "return items[0].json.results.map(r => ({ json: { name: r.name, address: r.formatted_address, rating: r.rating, place_id: r.place_id } }))"
      }
    },
    {
      "name": "Send to AI Scoring",
      "type": "n8n-nodes-base.httpRequest",
      "parameters": {
        "url": "http://localhost:5678/webhook/ai-score"
      }
    }
  ]
}
```

## 🧠 WF2 — IA Scoring + Firebase
Analyse les prospects avec OpenAI et les enregistre dans Firestore.

```json
{
  "name": "WF2_AI_SCORING_FIREBASE",
  "nodes": [
    {
      "name": "Webhook Input",
      "type": "n8n-nodes-base.webhook",
      "parameters": { "path": "ai-score" }
    },
    {
      "name": "OpenAI Scoring",
      "type": "n8n-nodes-base.openai",
      "parameters": {
        "model": "gpt-4o-mini",
        "prompt": "Analyse ce partenaire et donne un score 0-100 + sphères + potentiel abonnement : {{ $json }}"
      }
    },
    {
      "name": "IF Score > 40",
      "type": "n8n-nodes-base.if",
      "parameters": {
        "conditions": {
          "number": [
            {
              "value1": "={{$json.score}}",
              "operation": "larger",
              "value2": 40
            }
          ]
        }
      }
    },
    {
      "name": "Firebase Create Partner",
      "type": "n8n-nodes-base.httpRequest",
      "parameters": {
        "url": "https://firestore.googleapis.com/v1/projects/YOUR_PROJECT/databases/(default)/documents/partners",
        "method": "POST"
      }
    }
  ]
}
```

## 📩 WF3 — Email Automatique
Génère et envoie un email de prospection personnalisé dès qu'un nouveau partenaire est créé.

```json
{
  "name": "WF3_EMAIL_CONTACT_AUTOMATIQUE",
  "nodes": [
    {
      "name": "Trigger New Partner",
      "type": "n8n-nodes-base.firestoreTrigger"
    },
    {
      "name": "OpenAI Email Generator",
      "type": "n8n-nodes-base.openai",
      "parameters": {
        "prompt": "Écris un email commercial pour convertir ce partenaire en abonnement : {{ $json }}"
      }
    },
    {
      "name": "Send Email",
      "type": "n8n-nodes-base.gmail",
      "parameters": {
        "subject": "Visibilité locale pour votre activité",
        "message": "={{$json.email_content}}"
      }
    },
    {
      "name": "Update Status Contacted",
      "type": "n8n-nodes-base.httpRequest"
    }
  ]
}
```

## 🔁 WF4 — Relance Automatique
Relance les partenaires qui n'ont pas encore souscrit après 3 jours.

```json
{
  "name": "WF4_RELANCE_SEQUENTIELLE",
  "nodes": [
    {
      "name": "Wait 3 Days",
      "type": "n8n-nodes-base.wait",
      "parameters": { "waitTime": "3 days" }
    },
    {
      "name": "Check Payment Status",
      "type": "n8n-nodes-base.httpRequest"
    },
    {
      "name": "IF Not Paid",
      "type": "n8n-nodes-base.if"
    },
    {
      "name": "Send Follow-up Email",
      "type": "n8n-nodes-base.gmail"
    }
  ]
}
```

## 💳 WF5 — Stripe + Activation Automatique
Active la visibilité du partenaire dès réception du paiement Stripe.

```json
{
  "name": "WF5_STRIPE_ACTIVATION_FIREBASE",
  "nodes": [
    {
      "name": "Stripe Webhook",
      "type": "n8n-nodes-base.webhook",
      "parameters": { "path": "stripe-payment" }
    },
    {
      "name": "Update Firebase Active",
      "type": "n8n-nodes-base.httpRequest",
      "parameters": {
        "url": "https://firestore.googleapis.com/.../partners",
        "method": "PATCH",
        "body": {
          "status": "active",
          "payment_status": "paid",
          "visibility": true
        }
      }
    },
    {
      "name": "Send Confirmation Email",
      "type": "n8n-nodes-base.gmail"
    }
  ]
}
```

---
**Logique Globale :** Google Places → IA Scoring → Firebase (Prospect) → Email IA → Relances → Stripe → Activation auto.
