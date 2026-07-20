# ViriSIM Hash Verifier

Open-source browser tool to verify the cryptographic integrity of ViriSIM audit logs.

## Links

- **Live Verification Tool:** [https://virideed.github.io/virisim-hash-verify/](https://virideed.github.io/virisim-hash-verify/)
- **Get a Sample Audit:** [https://virideed.com/virisim/regulator-share?search=va8N1SPsEJRMnHNcIKq-regurlna5k9km9](https://virideed.com/virisim/regulator-share?search=va8N1SPsEJRMnHNcIKq-regurlna5k9km9)

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

- **Sample Audit:** Use the link above to download a sample audit from our regulator share page
- **Your Own Audit:** From your ViriSIM dashboard, click **"Download Hashed JSON"** or **"Copy Hash Data"** in the Additional Information section

### 2. Verify the Hash

1. Open the **Live Verification Tool**
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
