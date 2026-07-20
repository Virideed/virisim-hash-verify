# ViriSIM Hash Verifier

Open-source browser tool to verify the cryptographic integrity of ViriSIM audit logs.

**Repository:** [https://github.com/Virideed/virisim-hash-verify](https://github.com/Virideed/virisim-hash-verify)

**Live Tool:** [https://virideed.github.io/virisim-hash-verify/](https://virideed.github.io/virisim-hash-verify/) (enable GitHub Pages first)

---

## Features

- ✅ **Full Log Hash Verification** — Test computed hash against stored `integrityHash`
- ✅ **Chain Hash Verification** — Verify chain link with previous hashes
- ✅ **No dependencies** — Runs entirely in your browser, no server required
- ✅ **Load JSON file** — Upload your audit file directly
- ✅ **Open source** — Code is fully inspectable

---

## Usage

### 1. Get Your Audit JSON

Download your audit log from the **"Additional Information"** section of your ViriSIM audit report. Click **"Copy Hash Data"** or **"Download Hashed JSON"** to export the audit data.

### 2. Verify the Hash

1. Open `index.html` in your browser (or use the live link above)
2. Paste your audit JSON or upload the file
3. The **"Stored Hash"** field auto-populates from the audit
4. Click **"Compute & Test"** — Result shows ✅ MATCH or ❌ NO MATCH

### 3. Verify the Chain (Optional)

1. Enter the **Previous Integrity Hash** and **Previous Chain Hash** from the previous audit record
2. The **"Stored Chain Hash"** auto-populates
3. Click **"Verify Chain"** — Result shows ✅ CHAIN VALID or ❌ CHAIN BROKEN

---

## Verification Method

The tool builds a hashable payload by:

- Removing self-referential fields (`logIntegrity`, `integrity`, `meta.resolution`)
- Flattening all nested objects
- Sorting all keys alphabetically
- Normalizing arrays to consistent strings

---

## License

MIT
