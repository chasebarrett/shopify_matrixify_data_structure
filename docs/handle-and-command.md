## 🔄 Matrixify Import Guide: Handle & Command

### How Matrixify Matches Products

When exporting product data, Matrixify includes an **ID** column.

- The ID is Shopify’s internal product identifier
- If an import includes an ID, Matrixify will always match and update that exact product
- This is the safest way to update existing products

---

### What Happens Without an ID

If no ID is present, Matrixify falls back to the **Handle**.

- The handle defines the product’s URL (PDP)
- Matrixify uses the handle to determine whether to create or update a product
- The Handle and Command columns must be used together correctly

---

### Handle + Command Behavior

**Updating an existing product**
Handle: drago-xt
Command: UPDATE


Result:  
The existing *Drago XT* product is updated.

**Incorrect command**
Handle: drago-xt
Command: NEW


Result:  
A second *Drago XT* product is created, resulting in a duplicate PDP.

---

## 🧠 Key Takeaways

- Use **ID** whenever possible when updating existing products
- If no ID is present:
  - Ensure the handle matches the existing product
  - Use the correct command value
- Incorrect commands can unintentionally create duplicate products

---
```mermaid
flowchart TD
  A[Matrixify import row] --> B{ID present}

  B -->|Yes| C[Match exact product by ID]
  C --> D[Apply Command to matched product]

  B -->|No| E[No ID\Use Handle as identifier]
  E --> F{Command}

  F -->|UPDATE| U1[Find product by Handle]
  U1 --> U2[Update existing product]
  U2 --> U3[Outcome\Existing PDP updated]

  F -->|NEW| N1[Create new product]
  N1 --> N2[Use Handle for product URL]
  N2 --> N3[Outcome\New PDP created]
  N3 --> N4[Risk\If Handle already exists\Duplicate product may be created\nOr handle adjusted]

  F -->|DELETE| X1[Delete product]
  X1 --> X2[Matched by ID if present\Otherwise matched by Handle]
```
## 📚 Reference Documentation

Matrixify product documentation:  
https://matrixify.app/documentation/products/
