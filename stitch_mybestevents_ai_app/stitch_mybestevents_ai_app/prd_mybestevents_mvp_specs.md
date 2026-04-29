# MyBestEvents - Spécifications Techniques MVP

## 1. Structure FlutterFlow
- **Pages Utilisateur** : Splash, Login, Onboarding, Home, Explorer (Map), Partner Detail, Booking, Profile.
- **Pages Partenaire** : Dashboard, Edit Profile, Subscription.
- **Pages Admin** : Dashboard, Partner Management, Payments, Analytics.

## 2. Architecture Firebase
### Collections
- **users** : email, role (user/partner/admin), name, favorites, spheres (map), wellness_score.
- **partners** : name, category, sphere, location (latlng), city, price, rating, isPremium, isBoosted, status (active/prospect), payment_status.
- **events** : title, sphere, date, location, price, partner_ref.
- **bookings** : user_ref, event_ref, status, payment_status, amount.

## 3. Logique n8n (Automatisation)
- **WF1 (Acquisition)** : Google Places API -> IA Scoring -> Firebase (Prospect).
- **WF2 (Contact)** : Trigger Prospect -> Email IA personnalisée -> Status Update.
- **WF3 (Conversion)** : Stripe Webhook -> Activation Partner (Visibility: true) -> Firebase Update.

## 4. Design System
- **Primaire** : #2BB673 (Vert Vitalité)
- **Secondaire** : #1E3A8A (Bleu Tech)
- **CTA** : #FF8A4C (Orange Conversion)
- **Typographie** : Poppins & Inter.
