# Heresy 3.0 Legion Builder

A clean, offline-capable army list builder for the **Horus Heresy 3.0 Legiones
Astartes** — all 18 Space Marine Legions. Single-file vanilla-JS web app (no
frameworks), installable as a PWA.

This is the **Legions-only** build: no Aeldari/Asuryani army and no playtest
tooling (no per-unit OP/UP/OK balance tags). It is a deploy-only repository —
the encrypted datasheet bundles ship as ciphertext and are unlocked in-browser
with a passphrase.

## Use

Open the site, enter the passphrase, pick a Legion. Build under the real HH3.0
Crusade Force Organisation rules (detachments, prime advantages, Warlord / Lord
of War / Allied caps). Save/load lists locally, export/import JSON, share via
link, or switch to Play Mode at the table.

## Contents

- `index.html` — the whole app (UI, engine, styling).
- `app/data.enc.js` — encrypted bootstrap bundle (Dark Angels) loaded at the gate.
- `app/data.<legion>.enc.js` — encrypted per-Legion datasheet bundles.
- `app/crests/`, `app/icons/` — legion emblems and PWA icons.
- `sw.js`, `manifest.webmanifest` — offline service worker + PWA manifest.

All bundles are AES-256-GCM encrypted (PBKDF2-SHA256, 200k iterations) and
decrypted in-browser via Web Crypto. Plaintext rules are never committed.
