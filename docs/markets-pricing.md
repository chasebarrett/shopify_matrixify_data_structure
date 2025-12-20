## 🌎 Markets & Pricing (United States vs Canada)

Many stores in the United States sell in both the United States and Canada, but **pricing does not live in metafields**.

Even though you may have:
Variant Metafield: scp.ca_price
Variant Metafield: scp.us_price

These fields are **not used** for pricing imports or frontend pricing display.

---

### 🇨🇦 How Canadian Pricing Works in Shopify

Canadian pricing is controlled by two required Matrixify columns:

- `Included / Canada` → Boolean (`TRUE`)
- `Price / Canada` → Actual CAD price

Both columns must be populated for fixed Canadian pricing to import correctly.

If no fixed Canadian price exists, Shopify converts the U.S. price for the Canadian storefront.

---

### 🇺🇸 United States Pricing

The same logic applies to the U.S. market:

- `Included / United States` → Boolean (`TRUE`)
- `Price / United States` → Actual U.S. price

