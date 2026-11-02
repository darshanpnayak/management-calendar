# Management Calendar

A shared calendar for the management team: out-of-office, leave, business travel and remote days, plus company holidays, meetings and events.

- **The page:** `index.html`, hosted free on GitHub Pages.
- **The database:** `data/management-calendar.xlsx`, an Excel file kept in this repository.

## How it works

| Who | What they do |
|---|---|
| **Anyone with the link** | Views the calendar (month view or upcoming list), filters by person or type, and downloads the Excel file. |
| **Editors** | Click **Sign in to edit**, paste their GitHub token once, then add, edit or delete entries. Each save is committed straight into the Excel file in this repository. |
| **Excel users** | Can also edit `data/management-calendar.xlsx` directly (download it, edit it, then upload it back here with **Add file → Upload files**). |

Each change shows up as its own commit, such as `Add: Ranganath Shenoy – Out of office (2026-11-02 to 2026-11-04)`, so the repository history doubles as an audit log.

## One-time setup

1. **Create the repository.** On GitHub, go to **New repository**, name it `management-calendar`, and create it.
2. **Upload the files.** Use **Add file → Upload files** and drag in `index.html`, `README.md`, `.nojekyll` and the `data` folder. Then commit.
3. **Turn on GitHub Pages.** Go to **Settings → Pages**. Under *Source*, choose **Deploy from a branch**, pick **main** and **/ (root)**, then click **Save**.
   About a minute later the site is live at `https://<your-github-username>.github.io/management-calendar/`.
4. **Give editors access.** Add each editor under **Settings → Collaborators** with Write access.

## Editor token (each editor, once)

1. On GitHub, go to **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Fill it in:
   - **Repository access:** *Only select repositories*, then pick `management-calendar`.
   - **Permissions → Repository permissions → Contents:** *Read and write*.
   - **Expiration:** your choice, for example 90 days.
3. On the calendar page, click **Sign in to edit** and paste the token. The owner and repository name fill in automatically on GitHub Pages. Tick **Remember on this device** only on your own computer.

The token is stored only in that browser and is sent only to `api.github.com`.

## Editing the Excel file by hand

- Don't rename the sheets (`Entries`, `People`, `How to use`) or the column headers.
- **Type** must be one of: Out of office, Leave, Business travel, Remote / WFH, Company holiday, Meeting, Event.
- **Person** is needed for the first four types. **Title** is needed for Company holiday, Meeting and Event.
- **Start / End** should be real Excel dates. Text like `2026-11-10` or `10/11/2026` (dd/mm/yyyy) also works.
- Leave **ID** blank on new rows. The page assigns one on the next save.

Note: when the page saves, it rewrites the workbook. Column widths and data are kept, but the Excel dropdown lists on the Type and Person columns are not.

## Privacy

A GitHub Pages site is **publicly reachable by anyone who has the link**, even when the repository itself is private. The only exception is GitHub Enterprise Cloud with access control turned on. The Excel file can be downloaded from the site as well, so keep notes in it free of sensitive details.
