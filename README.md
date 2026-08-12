# ISUZU Bodyshop Andon (BODY Assy)

Real-time factory Andon for Body Assy. Master PC writes live production data; TV/monitor screens mirror it through **Firebase Realtime Database**.

## Live links

- GitHub: https://github.com/muhdsyhmi35-max/Body-Assy
- Firebase console: https://console.firebase.google.com/project/body-assy-andon/overview
- Hosting (after deploy): https://body-assy-andon.web.app

## Files

| File | Use |
|------|-----|
| `MASTER_CONTROL.html` / `index.html` | Master PC controls (writes to Firebase) |
| `TV_DISPLAY.html` | TV / monitor display (read-only sync) |
| `database.rules.json` | Realtime Database rules (open for testing) |
| `firebase.json` | Hosting + database deploy config |

## How to run

1. Open `MASTER_CONTROL.html` on the Master PC (or open the Hosting URL).
2. Open `TV_DISPLAY.html` on the TV PC (or `/TV_DISPLAY.html` on Hosting).
3. Both machines need internet.
4. Changes on Master (plan/actual/timer/spatter/respot) sync to TV through Firebase path `andon/liveState`.

## Firebase project

Configured for:

- Project ID: `body-assy-andon`
- Database: `https://body-assy-andon-default-rtdb.asia-southeast1.firebasedatabase.app`

## Deploy

```bash
firebase deploy --only database,hosting --project body-assy-andon
```

## Security note

Current Realtime Database rules allow open read/write for testing. Before production, tighten rules and get IT approval.

## Note about the older Firebase link

The console URL `body-assy---andon` is a different Firebase project and was not accessible from the CLI account used here (`muhdsyhmi35@gmail.com`). This app is published against the new accessible project `body-assy-andon`.
