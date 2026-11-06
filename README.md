# File Transfer Tracker / מעקב העברת קבצים

A Hebrew/English app for tracking file transfers by date and time range.

## Features
- Create lists per date, each with multiple time ranges
- Sort the date list by the list's date or by when it was added (grouped by day), newest or oldest first
- Add 3-digit file IDs and track status: Ready / Working / Lost
  - Typing the 3rd digit adds the ID automatically; paste a whole list at once
  - Duplicate IDs are blocked across all time ranges of a date
- Filter chips + stats counter per time range, "mark rest ready" bulk action
- Undo for removed IDs, deleted time ranges and bulk changes
- Export a formatted Hebrew message ready to copy-paste
- Dark mode toggle
- Language toggle (UI in EN/HE — export always in Hebrew)
- Data saved per device in browser localStorage

## Usage
Open `index.html` directly in any browser — no install needed.  
Data is saved locally in your browser (localStorage).

**Live site:** https://arcdemonx.github.io/file_tracker/

## Moving data after a username change
Data lives in the browser, tied to the site address (`<username>.github.io`), not to the repo. After a rename the app opens empty at the new address. The old data is still in the browser, under the old address.

`rescue.html` gets it back. It has to be served from the old address, then opened in the same browser:
1. Sign in to the GitHub account that now holds the old name (`PoH-rull`).
2. Go to https://github.com/new/import. Use `https://github.com/ArcDemonX/file_tracker` as the URL and `file_tracker` as the name, and make it **Public**.
3. In the imported repo: Settings → Pages → Deploy from a branch → `master` / root → Save. Wait about a minute.
4. Open https://poh-rull.github.io/file_tracker/rescue.html in the browser where you used the app. Tap **Download backup** first, then **Move to new site**.

Every page on `poh-rull.github.io` shares the same storage, so one rescue page sees both apps' data.
The page only reads storage. The move puts the data in the URL `#hash`, which is never sent to any server. Anything already at the new address is kept under a `.before-restore` key.
