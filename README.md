# Clam Finder — iOS

Native iOS wrapper (Capacitor) for the **Clam Finder** clamming & fishing app.
Built on **Codemagic's cloud Mac** — no Mac needed on your end.

## What's in here
- `www/` — the web app (`clamsight.html` + images). At build time Codemagic copies `clamsight.html` → `index.html` (the Capacitor entry point).
- `capacitor.config.json` — app id `com.clamfinder.app`, name **Clam Finder**.
- `codemagic.yaml` — the iOS build + TestFlight workflow.
- `app-icon-1024.png` — the app icon.

## How to build (your steps in Codemagic + App Store Connect)
1. **App Store Connect** → register App ID `com.clamfinder.app`, then create a new app called **Clam Finder** (Bundle ID `com.clamfinder.app`).
2. **Codemagic** → add this repo as an app. It auto-detects `codemagic.yaml`.
3. The workflow reuses your existing **`ParanormalPulse_ASC`** App Store Connect API key (one key works for every app in your developer account). If Codemagic doesn't show it, add your `.p8` key under *Settings → Integrations → App Store Connect* and name it exactly `ParanormalPulse_ASC`.
4. Start the **Clam Finder iOS** workflow → it signs, builds the `.ipa`, and uploads to **TestFlight**.
5. Promote from TestFlight to App Store review in App Store Connect (free listing + screenshots).

**Permissions requested:** Camera (AI Vision scan) · Location (nearest tide station).
