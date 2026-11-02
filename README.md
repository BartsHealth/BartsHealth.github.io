# Barts Wi-Fi Refresh Planner

A web page for the Wi-Fi access point refresh plan. `index.html` reads `Barts_WiFi_Refresh_Planner.xlsx` from the same folder every time it opens and works out the dates in the browser, using the same rules as the spreadsheet's formulas.

## Files

| File | What it is |
|---|---|
| `index.html` | The page |
| `Barts_WiFi_Refresh_Planner.xlsx` | The plan. Edit this to change what the page shows |
| `README.md` | This note |

## Publish on GitHub Pages

1. In the repository, choose **Add file → Upload files** and add `index.html` and `Barts_WiFi_Refresh_Planner.xlsx` (and this README). Commit.
2. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick **main** and **/ (root)**, then **Save**.
3. After a minute or two the page is at `https://<account>.github.io/<repository>/`.

## Updating the plan

Edit the spreadsheet in Excel (settings on the **Order of Works** tab; fixed dates, status and notes on the **Buildings** tab), save it with the same name, and upload it to the repository in place of the old copy. GitHub can take a few minutes to serve the new file.

The **Minutes per AP** drop-down on the page is for trying out different install times. It doesn't change the spreadsheet; the spreadsheet's own setting is marked in the list.

## Good to know

- The page version is shown under the title (now **1.2, 2 Nov 2026**). If the site still shows an older number after you upload a new `index.html`, wait a few minutes and refresh with Ctrl+F5.
- The spreadsheet is set to **20 minutes per AP**, and the comparison column on the page is the **20-min baseline**.
- The spreadsheet must keep its tab names (Order of Works, Buildings, Non-Working Days) and column headings, or the page can't read it. Adding notes or changing values is fine.
- The page loads its spreadsheet reader from `cdn.sheetjs.com`. If a network blocks that site, download `xlsx.full.min.js` from https://cdn.sheetjs.com/, upload it to the repository, and change the `<script src=…>` near the top of `index.html` to `xlsx.full.min.js`.
- Opening `index.html` straight from your computer can't read the spreadsheet automatically. The page will ask you to choose the file instead.
- A GitHub Pages site from a public repository can be seen by anyone with the link, and so can the spreadsheet.
