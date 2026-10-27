# RetailIQ — Commerce Intelligence, Reimagined

An interactive, responsive, portfolio-oriented dashboard showcasing **verified historical research outputs** from the Brazilian Olist E-Commerce dataset (2016–2018).

The original research stack — Python, SQL, DuckDB, statistical tests, scikit-learn — is **preserved**. The website provides a new presentation layer using precomputed research results; it **does not retrain models or access an operational commerce feed**.

## Run it now

1. Unzip the downloaded archive.
2. Open **index.html** in Chrome, Edge, or Safari. All chart logic and source data are bundled locally. Font loading may use Google Fonts when online, but the site still works offline with fallback fonts.
3. Alternatively, open the folder in VS Code and run `python -m http.server 8000` from the terminal. Open `http://localhost:8000`.

## Sections

- **Overview** — cinematic introduction, KPI cards and interactive discovery tiles.
- **Commerce analytics** — 15 recovered category rankings; toggle product value / units, click categories for drilldown, search the category table.
- **Customer DNA** — RFM and K-Means segment analysis, recency and frequency views, silhouette comparison.
- **Delivery intelligence** — year-filtered monthly late rates, state details, duration groups, and methodology note.
- **Predictive AI** — validation model comparison, real holdout confusion matrix, temporal split and candid limitations.
- **Research lab** — delivery punctuality versus satisfaction with nonparametric and bootstrap statistics.
- **Architecture & data** — SQL/data workflow, reconciliation audit, capability transparency, CSV and JSON export.
- **Project & developer** — independent project background, seven-step development journey, author credit, Olist Kaggle source, technology stack and honest research limitations. (No GitHub / live-link placeholder is displayed.)

Use **Ctrl+K** (or Cmd+K) to jump between chapters. Select **ⓘ** in the toolbar for dataset provenance and limitations.

## Publish on GitHub Pages

1. Create a public GitHub repository.
2. Upload the **contents** of this folder into the repository root so `index.html` appears at the top level (not nested inside an extra folder). This package includes `.nojekyll` to keep static files untouched.
3. Go to **Settings → Pages → Build and deployment**. Choose **Deploy from a branch**, select your `main` branch and the `/ (root)` folder. Save.
4. Your Pages URL usually follows `https://YOUR_USERNAME.github.io/YOUR_REPOSITORY/`. This app uses relative asset paths and hash chapter routes, so it works under that subpath.

## Publish on Render (static website)

1. Create a new GitHub repository and upload this entire folder (not the ZIP alone), keeping `index.html` at the repository root.
2. On [Render](https://dashboard.render.com), create a **New Static Site**, and connect the GitHub repository.
3. Set **Build Command** to `echo ready` and **Publish Directory** to `.` (a single dot).
4. Deploy. Render will provide a publicly accessible URL. The included `render.yaml` also describes an equivalent static-site service.

No Python server, CSV upload, database password or training process is required at website request time.

## Verified facts and caveats

- The **R$13,221,498.11** product merchandise value excludes freight; it is not total payment volume.
- **93,358** customers were profiled for RFM, versus **96,470** records in the valid-delivery analysis and **95,824** in the reviewed-order statistical study. The denominators differ by design.
- The exploratory timestamp-based late-delivery rate is **8.11%**, while the corrected calendar-date rate is **6.77%**. The year and state charts are clearly marked as timestamp-based exploratory figures; they must not be interpreted as the final date-based rate for each subgroup.
- The delivery-risk model is a **research baseline**, not a production risk engine. Holdout test ROC-AUC **0.6612**, PR-AUC **0.0760**, precision **8.0%**, recall **17.1%**.
- Only top categories and summary aggregates were available from the recovered research files; charts present those **actual** figures, never fabricated time series or individual observations.
- Design charts are frontend interactive displays of recovered facts; **real-time predictions, live transaction queries, and dynamic DuckDB lookups have not been connected** in this snapshot.

## Files

```text
index.html               The website and all eight chapter layouts
assets/styles.css        Responsive design, motion and visualizations
assets/app.js            Navigation, filters, charts, exports and keyboard controls
assets/data.js           Bundled verified research data (for direct file opening)
assets/favicon.svg       Branding
assets/preview.png       Original website preview image (unchanged)
data/research.json        Source data snapshot with explicit analysis bases
generate_data.py         Rebuilds research.json and data.js from reviewed historical outputs
render.yaml              Original Render static-site blueprint
.nojekyll                Disables GitHub Pages Jekyll processing
```

## Next engineering stage

To move beyond the static research showcase, integrate the existing **DuckDB database, preprocessing and trained model artifacts** into a server API, add data validation and versioned snapshots, and run model inference only on real saved model weights and supported feature pipelines. The current site intentionally makes no unsupported live-data claims.

## Preservation record (V2 → GitHub ready)

- The original seven sections, sidebar styles, chart/filter/search/download behavior, dataset, render.yaml, animations and original components are preserved.
- Modifications to **index.html**: one original-style navigation button, and one appended `page-about` section before the original closing `</main>`.
- Modifications to **assets/app.js**: only the `about` chapter label in the existing navigation dictionary; all other JavaScript remains byte-for-byte the same.
- Modifications to **assets/styles.css**: only appended `.about-*` styles and animations; all original CSS remains byte-for-byte intact.
- **assets/data.js**, **data/research.json**, **assets/favicon.svg** and **render.yaml** are identical to the V2 package.
- All public metrics shown remain precomputed historical analytical results. No live database/model connection has been added.

## Sidebar access on shorter laptop screens

The left navigation scrolls independently: place the pointer over the sidebar and scroll down to **Project & developer (08)**. You can also press **Ctrl+K** and search for **developer**, or open `index.html#about`. This corrects an overflow issue in the first GitHub-ready ZIP; it does not alter the original chapter visuals, interactive data or analytics logic.

## Minimal update after feedback (2026-10-28)

- Removed the unconfigured GitHub repository / live-link placeholder from the About chapter. The real Kaggle dataset link remains.
- Enabled independent sidebar scrolling so all eight sections are accessible at normal 100% browser zoom.
- Left existing chapters, animations, calculations, navigation appearance, source data and other interactions unchanged.
