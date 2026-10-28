# Tape Board

Copper tape circuit designer for 3D printed boards. Runs on Windows and Android.

Created by R. Heller · [Support on Buy Me a Coffee](https://buymeacoffee.com/Rheller82)

## Download

Go to the **Releases** page and grab:

- `Tape-Board-1.0.0-x64.exe` (installer) or the portable `.exe` for Windows
- `Tape-Board.apk` for Android (allow "install unknown apps" when prompted)

## How the builds work

Pushing to `main` runs GitHub Actions, which builds both apps. Download the results from the run's **Artifacts** section.
To publish a release, push a version tag:

```
git tag v1.0.0
git push origin v1.0.0
```

The app itself is a single file at `www/index.html`. Edit it and push; both builds pick it up.

## Run locally

```
npm install
npm start
```
