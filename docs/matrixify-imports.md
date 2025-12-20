## 📦 Matrixify Import Guide (Abbreviated)

When configuring imports via Matrixify, SCARPA primarily uses:

- **Native Shopify columns** (e.g. `Variant Barcode`)
- **Defined product metafields** (e.g. `Metafield: scp.xxx`)

**Additional notes**
- `scp` is the namespace used for supported metafields
- We do not currently rely on variant metafields for imports
- `magento.*` metafields appear in exports but are not actively used

---

## ✋ Manual vs Import Updates

Some data is faster and safer to manage directly in Shopify rather than via import, especially when formatting or validation is strict (e.g. metaobjects or list fields).

In these cases, manual updates reduce risk and save time.
