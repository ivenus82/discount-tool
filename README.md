# Discount Check Tool

Browser tool that compares the **actual discount on each bill** with the **allowed discount as per the offer** (Apple Hardware + Care plans).

All processing runs **inside the browser**. Files are never uploaded to any server.

## How to use
1. Open the tool (GitHub Pages link or `index.html`).
2. Upload 3 files:
   - **Sales Statement**: raw sales export (e.g. `Oct2026.xlsx`)
   - **Price & Discount Master**: `Price_Discount_Master_Q127.xlsx` (sheet `Price Master`)
   - **Item List**: `Item List.xlsx` (column `Sale Price` = current MRP)
3. Click **Run Discount Check**, then **Download Excel Report**.

## What it does
1. **Cleans the sales data:** removes footer rows, removes listed executives, maps sub-branches to main branches, and keeps only AAR / APP / APR branches.
2. **Decides Old or New MRP:** if the bill MRP is lower than the Item List MRP, the stock is Old MRP.
3. **Decides Cash or Loan:** from the Affordability / Scheme text (FIN, CREDIT, EMI, LOAN).
4. **Finds the matching offer rule** in the master: family + capacity + colour + MRP / version + valid dates.
5. **Calculates Extra discount:** Actual discount − Allowed discount. Round-off up to the tolerance is ignored.

Settings (executives to remove, branch mapping, tolerance and so on) are under **Settings** and are saved in your browser.

## New offer every quarter
Update `Price_Discount_Master_*.xlsx` (one row per offer rule). The tool itself does not change.

> Do **not** commit sales, item list or master Excel files to this repository. Keep only `index.html` and `README.md`.
