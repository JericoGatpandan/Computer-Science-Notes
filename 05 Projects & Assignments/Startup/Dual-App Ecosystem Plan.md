## 🔄 Dual-App Ecosystem Plan

[[Construction Material Price & Store Finder]]

### 1. **Inventory Manager App (for Hardware Stores)**

**Goal:** Help small stores digitize and update their inventory

- Track current stock (e.g., 10mm Rebar – 50 pcs)
- Input price, stock status, reorder level
- Simple, mobile-friendly UI (can work offline, sync later)

---

### 2. **MatSearch PH (for Buyers / Engineers)**

**Goal:** Help buyers search for materials across stores

- Pulls updated inventory from partner stores
- Shows who has stock, prices, location
- Searchable, filterable interface

---

## 🧠 Integration Concept (Genius Part):

When a store **finishes or updates** its inventory list:

- ✅ A button appears: **“Publish to MatSearch PH”**
- That sends data (item name, price, quantity) to the public app
- You become the **bridge** between supply (stores) and demand (engineers)

---

## 💥 Why This Is Big

| Problem                                  | Your Solution                      |
| ---------------------------------------- | ---------------------------------- |
| Stores don’t have inventory systems      | You give them one, simple and free |
| Engineers don’t know where to buy        | You show them updated info         |
| Prices & stock info are rarely real-time | You make it live & useful          |

---

## ✅ MVP Plan

### A. Inventory Manager App Features

For store owners or managers:

- 📦 Add/Edit/Delete materials (name, price, qty, unit)
- 📋 Set "last updated" time
- ✅ Button to **sync selected items** to MatSearch
- 🔒 Optional PIN login (no complex auth)

---

### B. MatSearch PH Integration

- Pulls items from "published" inventories only
    
- Shows:
    
    - Store name
    - Item name, unit price
    - Last updated
    - Location
    - Stock level (optional)

---

## 🧱 Firebase Structure (Suggestion)

```bash
stores/
  storeId/
    name
    location
    contact
    inventory/
      itemId/
        name
        price
        stock
        unit
        lastUpdated
        isPublishedToMatSearch: true
```

On MatSearch side, you filter for:

```js
where("isPublishedToMatSearch", "==", true)
```

---

## 🧰 Tech Stack You Can Use (Simple Version)

|App|Tech|
|---|---|
|Inventory App|HTML/CSS/JS or React + Firebase Firestore|
|MatSearch PH|Same or separate frontend project pulling shared Firestore data|
|Integration|Just a boolean flag (`isPublishedToMatSearch: true`)|
|Hosting|Netlify or Vercel|
|Auth (optional)|Firebase Auth or PIN per store|

---

## 📦 Bonus Ideas for Future

- Export inventory to Excel or PDF
- Barcode scanning for adding items
- Store dashboard with basic charts (daily sales, low stock alert)
- Let stores _only_ publish select items (not full inventory)

---

## 🪜 Next Step

Want help?

✅ I can:

- Map out a wireframe for both apps
- Build the Firestore schema
- Help with integration logic
- Suggest UI structure

You're **very close to building a real system** that could get adopted locally — and scale.

Let me know if you want:

1. Firebase structure diagram
2. Feature checklist for both apps
3. Basic UI layout or starter code
    
