# Guide de Build FlutterFlow — MyBestEvents (MVP)

Ce document récapitule la logique de configuration pour ton projet FlutterFlow.

## 🧱 1. Configuration Globale
- **Projet** : MyBestEvents
- **Design System** : Vitality & Leisure (Vert: #2BB673, Noir: #1E1E1E)
- **Navigation** : Bottom Nav pour les Users, Side Menu pour Admin/Partners.

## 👤 2. Authentification & Onboarding
### Splash Screen
- **Composant** : Logo au centre.
- **Action** : `Wait 2000ms` -> `Navigate to AuthCheck`.

### Auth Check
- **Logique** : `Is User Logged In?`
  - YES -> `Navigate to Home`.
  - NO -> `Navigate to Login`.

### Onboarding (Multi-step)
- **Composant** : PageView avec 3 étapes.
- **Data** : Save `spheres` (Map) dans la collection `users`.

## 🏠 3. Espace Utilisateur
### Home (Feed IA)
- **Query** : Firestore `events` & `partners`.
- **Tri** : Variable `ai_score` (calculé ou mocké en MVP).
- **Action** : Track clic (Update `user_behavior` collection).

### Explorer & Carte
- **Query** : Filtrage dynamique par `sphere`, `price`, et `geo_location`.
- **Google Maps** : Marker coloré selon la sphère.

## 🏪 4. Espace Partenaire (B2B)
### Dashboard
- **KPI** : `Count` des `bookings` liés au `partner_ref`.
- **Revenus** : `Sum` des `bookings.amount`.

### Gestion des Offres
- **CRUD** : Formulaire pour alimenter la collection `events`.

## 🧑‍💼 5. Espace Administrateur
### Dashboard Back-office
- **KPI Nationaux** : Agrégation de toute la collection `bookings` et `partners`.
- **Modération** : Switch `is_active` sur les documents `partners`.

## 🤖 6. Logique IA & n8n
- **Scoring** : Les scores sont calculés via n8n (WF2) et repoussés dans Firestore.
- **Notifications** : Déclenchées par n8n (WF3) via Firebase Cloud Messaging.

---
**Checklist Finale** :
- [ ] Firebase Connecté
- [ ] Firestore Collections créées
- [ ] Stripe Connecté dans FF
- [ ] Webhooks n8n configurés
- [ ] Assets images importés dans FF
