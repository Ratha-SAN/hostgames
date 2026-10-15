# WasmArcade

Bilingual (Khmer / English) launcher for 29 browser games (classic ports plus Ouk Khmer), hosted on Firebase Hosting.

- `public/index.html` is the whole site (single page, no build step).
- `firebase.json` configures Firebase Hosting.
- `.github/workflows/firebase-hosting.yml` deploys on every push to `main`, and posts a preview URL on pull requests.

## One-time setup

1. Create a Firebase project at https://console.firebase.google.com and note its project ID.
2. In Google Cloud console → IAM → Service accounts (same project), create a service account with the
   **Firebase Hosting Admin** role, then create a JSON key for it.
3. In this GitHub repo → Settings → Secrets and variables → Actions:
   - **Secrets** tab: add `FIREBASE_SERVICE_ACCOUNT` with the full contents of the JSON key.
   - **Variables** tab: add `FIREBASE_PROJECT_ID` with your project ID.
4. Push to `main` (or run the workflow manually from the Actions tab). The site goes live at
   `https://<project-id>.web.app`.

## Deploy by hand

```
npx firebase-tools login
npx firebase-tools deploy --only hosting --project <project-id>
```

The games themselves are hosted on third-party sites; this page only links to them.
