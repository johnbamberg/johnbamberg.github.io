# AustMS 2026 programme viewer

A single web page that shows the conference programme by session or by day. Participants tick the talks they want, and the page builds **My programme** for them. From there they can add it to their calendar, print it, or send themselves a link to open it on their phone.

The page reads the programme from a spreadsheet: either `programme.csv` in this folder, or a Google Sheet. You change the programme by editing the spreadsheet. You don't need to edit any code.

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The page. The settings are at the top of the `<script>` section (`CONFIG`). |
| `programme.csv` | **Sample** programme with made-up speakers, using the 2026 special sessions. Replace it with the real one. |
| `README.md` | This file. |

## 1. Put it on GitHub Pages

**If you already have a GitHub Pages site** (for example `yourname.github.io`), the quickest way is to add this folder to that repository as `austms2026/`. The page will then be at `https://yourname.github.io/austms2026/`.

**Or make a new repository:**

1. On GitHub, create a new public repository, for example `austms2026-programme`.
2. Choose **Add file → Upload files**, drag in `index.html` and `programme.csv`, and commit.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After a minute or two the site appears at `https://yourname.github.io/austms2026-programme/`.

## 2. Choose where the programme data lives

### Option A: a Google Sheet (recommended)

This works like your iframe workflow: edit the sheet, and the website follows.

1. Create a Google Sheet and use **File → Import → Upload** to load `programme.csv` as a starting point. Keep the header row.
2. Choose **File → Share → Publish to web**. Pick the programme tab (not "Entire document"), choose **Comma-separated values (.csv)**, and click **Publish**.
3. Copy the link it gives you. It ends in `output=csv`.
4. In `index.html`, find `dataUrl: "programme.csv",` near the top of the script and replace it with your link:
   ```js
   dataUrl: "https://docs.google.com/spreadsheets/d/e/XXXXXXXX/pub?gid=0&single=true&output=csv",
   ```
5. Commit the change. From now on you only edit the Google Sheet. Changes show on the site within about 5 minutes, because Google refreshes the published copy on its own schedule.

Anyone with the link can read the published tab. Keep organiser emails and private notes on a **different tab** that you don't publish.

### Option B: the CSV file in this repository

Edit `programme.csv` in Excel or Google Sheets, export or save it as CSV, and upload it to GitHub again, replacing the old one. GitHub keeps every earlier version.

## 3. Spreadsheet columns

The header row names the columns. Their order doesn't matter, and capitals and spaces are ignored.

| Column | Needed? | Examples |
|---|---|---|
| `id` | Strongly recommended | `T001`, `T002`, … Any short code. **Never change or reuse an ID once the page is live.** People's saved picks are stored by ID. |
| `date` | Yes | `2026-12-01`, `1/12/2026`, `Tuesday 1 December 2026`, `Tuesday`, `Day 1` |
| `start` | Yes | `13:30`, `1:30 PM`, or a range like `13:30–14:00` (then `end` can be left out) |
| `end` | No | `14:00`. If it's missing, the talk is assumed to be 30 minutes. |
| `session` | Yes | Must be spelt the same way on every row of that session. It becomes the drop-down menu. |
| `speaker` | Yes | `Dr Jane Smith` |
| `affiliation` | No | Shown in small text under the speaker. |
| `title` | Yes | Can contain LaTeX, e.g. `Units in $\mathbb{Z}[\zeta_p]$` |
| `room` | No | `TLC-314` |
| `abstract` | No | If present, the title becomes clickable and opens the abstract. LaTeX works here too. |

Plenary lectures: give them the session name `Plenary lectures`. That session is listed first in the menu (see `pinnedSessions` in the settings).

If a row can't be read (for example, a date typo), it is skipped. While `showDataWarnings` is `true`, the page footer lists the skipped rows so you can fix them.

## 4. Link it from austms2026.org.au

Ask whoever manages the WordPress site (the UWA Data Institute) to add a **Programme** menu item that links to your GitHub page.

Linking is better than embedding the page in an iframe. Browsers restrict saved data inside embedded frames, so ticked talks may not be remembered there, and the page is easier to use on phones at full size.

Optional: the page can have its own address such as `programme.austms2026.org.au`. This needs a DNS record from whoever controls the domain, plus **Settings → Pages → Custom domain** on GitHub.

## 5. Settings (top of the script in `index.html`)

| Setting | What it does |
|---|---|
| `dataUrl` | Where the programme comes from (see section 2). |
| `title`, `subtitle`, `siteUrl` | The text at the top and the link in the footer. |
| `notice` | The orange "Sample data" box. **Set it to `""` when the real programme goes in.** |
| `conferenceDates` | The four conference days (used for the *By day* buttons). |
| `utcOffset` | `+08:00` for Perth. Used for calendar files. |
| `pinnedSessions` | Sessions listed first in the menu. The rest are alphabetical. |
| `showDataWarnings` | Set to `false` once the programme is final. |

To change the colours, edit the variables at the top of the `<style>` section (`--accent`, `--head`, and so on). Both light and dark mode are set there.

## What participants can do

- **By session:** pick a special session from the menu and see its talks day by day.
- **By day:** see every parallel talk grouped by start time. This is useful for hopping between sessions.
- **Search:** type a surname, a word from a title, or a room.
- **Tick talks:** picks are saved in the participant's browser. They don't need an account, and no data is sent anywhere.
- **My programme:** shows the picks in time order and flags talks that overlap. From there they can:
  - **Add to calendar (.ics):** one file that imports into Google, Outlook or Apple calendars, with times and rooms.
  - **Print / save as PDF.**
  - **Copy link:** a link containing their picks. Opening it on a phone loads the same programme there.
- Links to a session (`…/#session=Number%20theory`) or a day (`…/#day=2026-12-02`) can be shared. Session organisers can post a direct link to their session.

## Testing on your own computer

Opening `index.html` by double-clicking won't work, because browsers block a local page from reading `programme.csv`. Instead, open a terminal in this folder and run:

```
python3 -m http.server
```

Then go to <http://localhost:8000>.
