# Rice Portion Calculator

A mobile-first Progressive Web App (PWA) that distributes all cooked rice proportionally between two people and their requested meals.

## What it does

Enter:

- Total cooked rice in grams
- Person 1 grams per meal
- Person 1 number of meals
- Person 2 grams per meal
- Person 2 number of meals

The app calculates:

`scaling factor = total cooked rice ÷ requested total`

Each requested meal is multiplied by that factor. This preserves the requested Person 1 : Person 2 ratio while distributing all cooked rice.

## File structure

```text
rice-portion-calculator-pwa/
├── index.html
├── manifest.json
├── service-worker.js
├── README.md
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

## Upload to GitHub Pages

1. Create a GitHub repository.
2. Upload the contents of this folder, keeping the `icons/` folder and all files in place.
3. In the repository, open **Settings → Pages**.
4. Choose **Deploy from a branch**, select the branch containing these files, and choose the root folder.
5. Open the published Pages address after GitHub finishes deploying.

## HTTPS and PWA installation

Normal PWA installation requires the site to be served from a secure context (HTTPS). GitHub Pages provides HTTPS for its published site.

The app also works directly as a normal web page when opened locally, but service-worker/PWA installation behavior depends on the browser's secure-context rules.

## Install on Chrome for Android

1. Open the hosted HTTPS site in Chrome on Android.
2. Allow the first visit to finish so the service worker can cache the app.
3. Use Chrome's **Install app** / **Add to Home screen** option when offered.
4. Launch the installed app from the home screen. It can continue working offline after the first successful cached visit.

## Offline behavior

The service worker caches the app shell, manifest, and both icons during installation. On later visits, cached files are used when available, allowing the calculator to work without an internet connection.
