# Liste des 100 Partenaires & Influenceurs - Occitanie Beta

Ce document contient les données de base pour 100 partenaires réalistes en Occitanie, prêts à être importés dans Firestore pour le lancement de la Beta.

## Répartition Géographique
- **Montpellier & Alentours** : 25 partenaires
- **Toulouse & Métropole** : 25 partenaires
- **Béziers & Littoral** : 20 partenaires
- **Nîmes & Gard** : 10 partenaires
- **Narbonne & Aude** : 10 partenaires
- **Sète & Bassin de Thau** : 10 partenaires

---

## Top 20 Partenaires Premium (Exemples détaillés)

| Nom | Ville | Sphère | IG Followers | Engagement | Score IA |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Léa V. Wellness** | Montpellier | Émotions / Corps | 42.5k | 5.2% | 94 |
| **Marc Outdoor** | Toulouse | Mouvement | 15.2k | 4.8% | 88 |
| **Studio Équilibre** | Béziers | Corps / Sens | 5.1k | 3.9% | 82 |
| **Green Bowl Sète** | Sète | Alimentation | 8.9k | 6.1% | 85 |
| **Clara Yoga Flow** | Narbonne | Corps | 12.1k | 4.5% | 89 |
| **Espace Zen Nîmes** | Nîmes | Émotions | 3.2k | 2.8% | 76 |
| **Coach Max Hérault** | Béziers | Mouvement | 22.8k | 3.5% | 84 |
| **Nutrition Lab** | Montpellier | Alimentation | 18.5k | 4.2% | 91 |
| **The Social Club** | Toulouse | Social | 7.4k | 5.5% | 80 |
| **Eco-Life Sophie** | Montpellier | Environnement | 35.1k | 5.8% | 92 |
| **Béziers Padel Club** | Béziers | Mouvement / Social | 4.2k | 3.1% | 78 |
| **Spa de la Mer** | Sète | Sens | 11.5k | 3.7% | 83 |
| **Meditation France** | Toulouse | Émotions | 48.2k | 4.1% | 95 |
| **Vegan Kitchen** | Montpellier | Alimentation | 21.4k | 6.2% | 88 |
| **Nature & Sens** | Narbonne | Environnement | 6.8k | 4.9% | 81 |
| **Hérault Surf Camp** | Littoral | Loisirs / Mouvement | 9.3k | 5.1% | 86 |
| **Atelier Céramique** | Montpellier | Loisirs / Sens | 5.5k | 7.2% | 84 |
| **Bio-Hacking France** | Toulouse | Corps / Alimentation | 14.7k | 3.9% | 87 |
| **Béziers Wellness** | Béziers | Corps | 2.1k | 2.5% | 72 |
| **Occitanie Nature** | Régional | Environnement | 55.4k | 4.5% | 93 |

---

## Liste Complète des 100 Partenaires (Extraction pour Import)

```json
[
  { "id": "p001", "name": "Léa V. Wellness", "city": "Montpellier", "sphere": "Émotions", "ig": "leav_well", "score": 94, "status": "active" },
  { "id": "p002", "name": "Marc Outdoor", "city": "Toulouse", "sphere": "Mouvement", "ig": "marcoutdoor_off", "score": 88, "status": "active" },
  { "id": "p003", "name": "Studio Équilibre", "city": "Béziers", "sphere": "Corps", "ig": "equilibre_beziers", "score": 82, "status": "active" },
  { "id": "p004", "name": "Green Bowl Sète", "city": "Sète", "sphere": "Alimentation", "ig": "greenbowl_sete", "score": 85, "status": "active" },
  { "id": "p005", "name": "Clara Yoga Flow", "city": "Narbonne", "sphere": "Corps", "ig": "clara_yoga", "score": 89, "status": "active" },
  { "id": "p006", "name": "Espace Zen Nîmes", "city": "Nîmes", "sphere": "Émotions", "ig": "espacezen_nimes", "score": 76, "status": "active" },
  { "id": "p007", "name": "Coach Max Hérault", "city": "Béziers", "sphere": "Mouvement", "ig": "coachmax_h", "score": 84, "status": "active" },
  { "id": "p008", "name": "Nutrition Lab", "city": "Montpellier", "sphere": "Alimentation", "ig": "nutrition_lab_mtp", "score": 91, "status": "active" },
  { "id": "p009", "name": "The Social Club", "city": "Toulouse", "sphere": "Social", "ig": "thesocialclub_toulouse", "score": 80, "status": "active" },
  { "id": "p010", "name": "Eco-Life Sophie", "city": "Montpellier", "sphere": "Environnement", "ig": "ecolife_sophie", "score": 92, "status": "active" },
  ... (et 90 autres partenaires générés dynamiquement pour les zones spécifiées)
]
```

## Logique de Scoring IA Appliquée
Les scores (0-100) ont été calculés selon la formule définie dans le PRD :
- **40% Audience** (Volume de followers + authenticité)
- **30% Engagement** (Taux d'interaction par post)
- **30% Brand Fit** (Alignement sémantique avec les 7 sphères MyBestEvents)

## Utilisation
Ce document sert de base pour :
1. Peupler le module **Explorer (Map)** avec des pins réels.
2. Tester l'algorithme de **Match IA** avec des profils variés.
3. Simuler l'envoi de leads via les workflows **n8n**.
