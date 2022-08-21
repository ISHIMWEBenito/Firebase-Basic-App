# Firebase Application
# MY CLOUD FIRESTORE RULES

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if false
    }
    
    match /things/{docId} {
    allow write: if request.auth.uid == request.resource.data.uid;
    allow read: if request.auth.uid == resource.data.uid;
    }
  }
}

# npm

npm i firebase-tools -g
firebase init
firebase serve
firebase deploy
