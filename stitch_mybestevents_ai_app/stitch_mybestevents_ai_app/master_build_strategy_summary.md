# MyBestEvents - Master Build & Strategy Document

## 1. Project Overview
MyBestEvents is a high-fidelity wellness marketplace connecting users with local partners and events through AI-driven matching.

## 2. Technical Stack
- **Frontend**: FlutterFlow
- **Backend**: Firebase (Auth, Firestore, Storage)
- **Automation**: n8n
- **Intelligence**: OpenAI API

## 3. Core Architecture
### Firebase Collections
- **users**: profile, interests (7 spheres), wellness score.
- **partners**: business details, location, AI score, subscription status.
- **events**: schedules, pricing, partner reference.
- **bookings**: transaction history, status.
- **leads**: conversion tracking.

## 4. Key Workflows (n8n)
1. **Acquisition**: Google Places → IA Scoring → Firebase (Prospect).
2. **Engagement**: Automatic AI Email → Sequential Follow-ups.
3. **Conversion**: Stripe Payment → Auto-Activation in Firebase.

## 5. Design System
- **Primary**: #2BB673 (Vitality Green)
- **Secondary**: #1E3A8A (Tech Blue)
- **CTA**: #FF8A4C (Conversion Orange)
- **Typography**: Poppins & Inter.

## 6. Business Strategy
- **Target**: 100 Partners @ €49/mo + 300 User Subs @ €9.99/mo + Booking Commissions.
- **Goal**: €10,000/month recurring revenue.
