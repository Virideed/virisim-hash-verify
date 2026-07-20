# ViriSIM Hash Verifier

Open-source browser tool to verify the cryptographic integrity of ViriSIM audit logs.

## Features

- ✅ **Full Log Hash Verification** — Test computed hash against stored `integrityHash`
- ✅ **Chain Hash Verification** — Verify chain link with previous hashes
- ✅ **No dependencies** — Runs entirely in your browser, no server required
- ✅ **Load JSON file** — Upload your audit file directly
- ✅ **Open source** — Code is fully inspectable

## Usage

1. Open `index.html` in any modern browser
2. Paste your audit JSON or upload a file
3. Enter the stored hash(es) from the audit
4. Click **Verify**

## Verification

The tool builds a hashable payload by:
- Removing self-referential fields (`logIntegrity`, `integrity`, `meta.resolution`)
- Flattening all nested objects
- Sorting all keys alphabetically
- Normalizing arrays to consistent strings

## License

MIT
