# Gift Card Ledger

An offline-first PWA for tracking gift card balances, codes and checkout barcodes.

## No card data is in this repo

The app reads its cards from `payload.js`, an **encrypted** blob you generate yourself.
That file is gitignored and is never committed — neither are any plaintext exports.
A fresh clone of this repo contains the app and nothing about your cards.

## Loading your cards

1. Open `pack.html` locally in a browser.
2. Give it your plaintext ledger JSON and a passphrase. Encryption happens in the
   browser; nothing is uploaded.
3. Save the resulting `payload.js` next to `index.html`.
4. Open `index.html` and unlock with the same passphrase.

Without `payload.js` the app loads and runs, just with an empty ledger.

## Deploying

Every file is static and self-contained, so any static host works. For GitHub Pages,
serve from the repository root on the default branch — `.nojekyll` is already present
so the underscore-prefixed paths are left alone.

If you want the deployed copy to carry your cards, drop your generated `payload.js`
into the deployment separately. Think hard before committing it: it is encrypted, but
it is still your entire ledger sitting in a git history forever.
