# BillBook — Week 2 Project 7

## Run on a computer
For best results use a local server because service workers and PWA installation require localhost or HTTPS.
1. Extract the ZIP.
2. Open a terminal in this folder.
3. Run `py -m http.server 8000`
4. Visit `http://localhost:8000` in Chrome or Edge.

## Install on Android
Host the folder on an HTTPS static host (for example GitHub Pages), open the URL in Chrome on Android, then use browser menu → Install app / Add to Home screen. Open it once while online so the app shell is cached. Then test airplane mode.

## Features
Shop profile and UPI ID; item catalogue; bills with quantities, discounts and tax; UPI payment URI/QR; bill image sharing/download; bill history; daily sales; localStorage persistence; PWA manifest and service worker.

## Important limitations
- The three key calculations are local. Bills are stored only in this browser/device; there is no cloud sync or automatic backup.
- QR generation uses QRCode.js from a CDN. The first launch needs internet to load that library; after a successful load, the service worker can cache it for subsequent offline use. Test the QR specifically in airplane mode before claiming fully offline QR generation.
- The app creates a UPI payment request QR only. It does not verify payments or process money. Scan with a UPI app and verify the merchant name and amount before any real payment.
- Android installation requires HTTPS hosting or localhost. Opening index.html directly does not install as a PWA.
