# AustMS 2026 programme viewer

A single web page that shows the conference programme by session or by day. Participants tick the talks they want, and the page builds **My programme** for them. From there they can add it to their calendar, print it, or send themselves a link to open it on their phone.

The page reads `programme.json`, the talk list exported from the registration system. Talks that don't have a time yet are still listed under their session, and they move into place once they're timetabled.

## Files

| File | What it is |
|---|---|
| `index.html` | The page. The settings are at the top of the `<script>` section (`CONFIG`). |
| `programme.json` | The public copy of the 3 November export: 297 accepted talks with affiliations, 13 of them with a time (7 with a room). |
| `README.md` | This file. |

## 1. Put it on GitHub Pages

Add this folder to your GitHub Pages repository (for example as `austms2026/`), or make a new repository and turn on **Settings → Pages → Deploy from a branch → `main` / root**. The page appears at `https://yourname.github.io/austms2026/` a minute or two after each upload.

## 2. Updating the programme

Do this each time the talks or the timetable change:

1. Export the talks as JSON from the registration system.
2. Open the website with `#check` on the end of the address (`https://yourname.github.io/austms2026/#check`). Choose the export with **Check a new export from your computer**. The file stays on your computer; nothing is uploaded.
3. Read the **Problems** list (see section 4) and fix anything in the registration system first if needed. **Preview the website with this file** shows how the programme will look.
4. Click **Download programme.json for the website**.
5. Upload that `programme.json` to the repository, replacing the old one.

**Why not upload the export directly?** The page can read it as it is, but the export also contains each speaker's student status, their available days, and talks that are "Not Reviewed". Anyone can open a file on a public website. The downloaded copy keeps only what the programme shows: session, speaker, affiliation, authors, title, abstract, keynote flag, time and room. It also leaves out talks that aren't accepted.

## 3. Timetabling

The page takes the time of each talk from the export's `timetabled` field, for example `Wednesday 13:30:00`. The day name is matched to the conference dates (Tuesday = 1 December, and so on).

- **No time yet:** the talk is listed under its session as *not yet scheduled*. People can tick it, and it shows in their programme under "Not yet scheduled" until it gets a time.
- **End times** are the start time plus the talk length: `defaultMinutes` (30) for an ordinary talk, `keynoteMinutes` (60) for talks with `keynote` = 1, or a session's own `minutes` (plenaries and the public lecture are set to 60). A value like `Wed 15:30-16:30` sets the end time directly.
- **Other formats that work:** `Wed 13:30`, `2026-12-02 13:30`, `1:30 PM Wednesday`.
- **Rooms** come from each talk's `room` field in `programme.json`. A session's `room` in the settings is used for any of its talks whose `room` is empty, which saves typing the same room 20 times. The Room column only appears once rooms are known.
- **Affiliations** come from each talk's `affiliation` field and are shown under the speaker's name. `add_fields.py` in the LaTeX booklet folder adds both fields to `programme.json` and fills in affiliations from `registrants.tex`.

## 4. What the check page looks for

| Problem | Meaning |
|---|---|
| Speaker double-booked | The same speaker has two talks at overlapping times. |
| Overlap in a session | Two talks in the same session (and room) overlap. |
| Speaker not available | A talk is on a day the speaker didn't list as available. This check only works with the full export, not the public copy. |
| Unreadable time | The `timetabled` value couldn't be read as a day and time. |
| Unknown session code | A session code isn't in the `sessions` list in the settings. |
| Placeholder title | The title is "TBA" or just the speaker's name. |
| Not on the website yet *(note)* | Sessions where no talk is accepted yet, so they don't appear. |
| No affiliation *(note)* | Talks whose `affiliation` field is empty. |
| No abstract *(note)* | Talks with an empty abstract. |

In the 3 November export, **Geometric Analysis, Functional Analysis, Ergodic Theory and Dynamical Systems** and the **EDI panel** are entirely "Not Reviewed", so they don't appear on the website yet. They'll appear once their talks are accepted, or straight away if you set `showStatuses: []`.

## 5. Settings (top of the script in `index.html`)

| Setting | What it does |
|---|---|
| `dataUrl` | The data file, `programme.json`. |
| `notice` | The orange box under the title. Set to `""` to hide it. |
| `showStatuses` | Which values of the export's `accepted` field are shown. `["Accepted"]` by default; `[]` shows every talk. |
| `conferenceDates` | The four conference days. |
| `defaultMinutes`, `keynoteMinutes` | Talk lengths, used for end times. |
| `sessions` | One line per session code in the export: the name shown on the page, the room, and optionally `minutes`. The menu follows this order. |
| `title`, `subtitle`, `siteUrl` | The text at the top and the link in the footer. |

To change the colours, edit the variables at the top of the `<style>` section.

## Good to know

- **Ticked talks are remembered by an ID** made from the speaker's name (without Dr/Prof) and the session code. Ticks survive title corrections and timetabling. If a speaker moves to another session, that talk gets a new ID, and anyone who ticked it would need to tick it again. If the registration system can add an `id` field to the export, the page uses that instead.
- **LaTeX:** maths in titles and abstracts is typeset by MathJax. Text-mode LaTeX is converted too: `\emph`, `\textbf`, accents such as `Schr\"odinger`, `\href`, `--`, ``` ``quotes'' ```, `\cite`, lists and `thebibliography`.
- **Co-authors:** when the `authors` field lists more than the speaker, the abstract panel starts with "Authors: …".
- **CSV still works.** If you ever point `dataUrl` at a CSV file (or a Google Sheet published as CSV), the page reads that too.

## What participants can do

- **By session:** pick a session from the menu and see its talks day by day, with any not-yet-scheduled talks underneath.
- **By day:** see every talk on a day, grouped by start time. This is useful for moving between parallel sessions.
- **Search:** search speakers, co-authors, titles and rooms.
- **My programme:** shows the ticked talks in time order and flags any that overlap. From there they can:
  - **Add to calendar (.ics):** a calendar file containing the ticked talks that have a time.
  - **Print / save as PDF.**
  - **Copy link:** a link containing their ticked talks. Opening it on a phone loads the same programme there.
- Links to a session (`…/#session=Number%20theory`) or a day (`…/#day=2026-12-02`) can be shared.

## Linking from austms2026.org.au

Ask the UWA Data Institute to add a **Programme** menu item that links to your GitHub page. Linking is better than embedding the page in an iframe: browsers restrict saved data inside embedded frames, so ticked talks may not be remembered there.

## Testing on your own computer

Double-clicking `index.html` won't work, because browsers block a local page from reading `programme.json`. Instead, open a terminal in this folder, run `python3 -m http.server`, and go to <http://localhost:8000>.
