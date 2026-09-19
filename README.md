# SKYBOUND

Static browser parkour game with Firebase Authentication and a live Firestore leaderboard.

## Firebase setup

1. Open the Firebase project named in `.firebaserc` and register the GitHub Pages URL in Authentication > Settings > Authorized domains. Add `localhost` for local testing.
2. In Authentication > Sign-in method, enable **Google** and **Anonymous**. The Google consent screen must be configured.
3. Deploy the leaderboard rules from this directory:

```powershell
firebase login
firebase deploy --only firestore:rules
```

4. Open `index.html` through a local web server or GitHub Pages. Do not use `file://`, because Google sign-in requires an authorized HTTP(S) origin.

The Firebase Web App Config in `index.html` is public client configuration. Never add a service-account JSON file, private key, or other server credential to this repository.

## GitHub Pages

Push the `skybound` directory to a GitHub repository, then configure Pages to deploy that directory (or make it the repository root). Add the resulting `https://<owner>.github.io` domain to Firebase Authentication before testing Google login.
