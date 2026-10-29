# StockSense AI — Smart Inventory and Stock Monitoring System

**Problem:** Small shops and warehouses track stock on paper or spreadsheets, causing stockouts, expired goods and overstocking.
**Objectives:** central inventory, low-stock + expiry alerts, demand-based reorder suggestions, clear analytics.

## Run (VS Code)
1. Open the `stocksense-ai` folder in VS Code. 2. Install the **Live Server** extension. 3. Right-click `login.html` → *Open with Live Server*. 4. Click **Use demo login**. (Internet needed once for the Chart.js CDN.)

## Architecture
Pure front-end: HTML5 + CSS3 + vanilla JS. `js/data.js` = sample data + LocalStorage load/seed; `js/app.js` = business logic (status, forecast, stock movement) + views + hash router. All state lives in one object `S`, saved to LocalStorage under `stocksense_v1`. Every stock change goes through `move()` so totals and history never diverge.

## Requirements
Functional: CRUD products, stock in/out (no negatives), PO workflow (stock added once on Received), alerts, FEFO, forecasts, warehouse map, CSV export, theme, reset.
Non-functional: responsive, runs offline after first load, beginner-readable code, no API keys. Demo login and forecasts are **not** production-secure / real AI.

## Test checklist
- [ ] Login (demo + validation) · [ ] Add product with invalid data shows error · [ ] Edit/delete (confirm) · [ ] Search/filter/sort/paginate
- [ ] Stock Out above quantity is rejected · [ ] Stock In updates dashboard + timeline · [ ] Mark PO Received → stock +once, dropdown locks
- [ ] Create PO from Reorder page · [ ] Expiry Radar order · [ ] Click warehouse shelves · [ ] Notification View buttons
- [ ] Dark mode · [ ] CSV export · [ ] Reset demo data · [ ] Resize to mobile width

## Future enhancements
Real backend + authentication, barcode scanning, real ML forecasting, multi-warehouse, email alerts, role-based access.
