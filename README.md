# QF Values dashboard

A view-only dashboard for the QF/LED Values tab of the QF Values Master Google Sheet. It shows the latest QF and LED readings for SLE, Low Green Export, Cooling Crystalliser, TJ Export and Main Dissolver, along with their QF limits, a trend chart and the recent entries. It reloads the sheet every 5 minutes.

The page only reads a published CSV copy of one tab. Nobody can edit the sheet from it.

## Setup

1. **Publish the tab.** In the Google Sheet, go to File → Share → Publish to web. Under "Link", pick the **QF/LED Values** tab and **Comma-separated values (.csv)**, then press Publish and copy the link.
2. **Paste the link.** Open `index.html` and set `csvUrl` in the `CONFIG` block near the bottom.
3. **Push to GitHub.** Push this folder to a GitHub repo, then go to Settings → Pages → Build and deployment and set Source to "Deploy from a branch", with branch `main` and folder `/ (root)`. The site appears at `https://<your-username>.github.io/<repo>/`.

## Changing limits

Edit the `UNITS` list in `index.html`. Each unit has `lo` and `hi` in %. A unit with no `lo`/`hi`, such as Main Dissolver for now, shows "No limits set".

## Good to know

- Google refreshes a published CSV a few minutes after the sheet changes, so new entries can take up to about 5 minutes to reach Google, plus up to 5 more for the page to pick them up.
- GitHub Pages sites are public, and anyone who views the page source can see the CSV link. That link exposes only the QF/LED Values tab and is read-only. Stop publishing the tab in Google Sheets at any time to cut access.
