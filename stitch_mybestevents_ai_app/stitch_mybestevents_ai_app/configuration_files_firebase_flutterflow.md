# MyBestEvents - Fichiers de Configuration MVP

## 🔐 Firebase Security Rules
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    match /partners/{partnerId} {
      allow read: if true;
      allow write: if request.auth != null && (request.auth.token.admin == true || request.auth.uid == partnerId);
    }
    match /events/{eventId} {
      allow read: if true;
      allow write: if request.auth != null && request.auth.token.partner == true;
    }
    match /leads/{leadId} {
      allow read: if request.auth != null && (request.auth.token.admin == true || request.auth.token.partner == true);
      allow write: if true; // Inscriptions publiques
    }
  }
}
```

## 📦 FlutterFlow Export Logic (JSON Structure)
```json
{
  "project": "MyBestEvents_MVP",
  "theme": { "primary": "#2BB673", "secondary": "#1E3A8A" },
  "routes": [
    { "path": "/", "page": "Splash" },
    { "path": "/home", "page": "UserHome" },
    { "path": "/match", "page": "IAMatch" },
    { "path": "/admin", "page": "AdminDashboard" }
  ],
  "collections": ["users", "partners", "events", "bookings", "leads"]
}
```