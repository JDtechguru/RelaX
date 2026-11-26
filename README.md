# RelaX – setup guide

*Team leave, made easy.*

A shared leave calendar that runs on your team's phones. It's hosted free on your own GitHub account, with no WBD systems involved.

- **Calendar:** Week, Month and Year views. Each day shows how many people are off; half days count as ½.
- **Leave types:** Leave, Half day (AM/PM) and Summer Hours. You can add more in Settings.
- **Days not counted:** weekends and holidays are greyed out and left out of the counts.
- **Filters:** filter by person and by leave type.
- **Reports:** set any date range to see a summary and the busiest days, then export to Excel.
- **Access:** viewers need the **team passcode**. Admins also need the **edit key**.
- **About tab:** a built-in how-to guide for the team, plus app credits (Jaydeep Saha, Senior, Photo Editorial).
- **Look:** calm Sage theme with soft gradients, frosted-glass panels and gentle tap animations. Animations switch off automatically if a phone has *Reduce motion* turned on.
- **Privacy:** the leave data is **encrypted** with the team passcode before it's stored on GitHub.

---

## Files in this folder

| File | What it is |
|---|---|
| `index.html` | The app |
| `sw.js` | Lets the app open without a signal |
| `manifest.webmanifest` | Makes it installable on phones |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | App icons |
| `README.md` | This guide |

You won't upload any data file. The app creates its own (`data.enc.json`) the first time you set it up.

---

## One-time setup (owner, about 15 minutes)

### Step 1 – Create the repository
1. Sign in at **github.com** and click **+** (top right), then **New repository**.
2. Fill it in:
   - **Repository name:** `relax`. Any name works; it becomes part of the link.
   - Set it to **Public**. Free GitHub hosting needs this, and the leave data stays encrypted.
3. Click **Create repository**.

### Step 2 – Upload the app files
1. On the new repository page, click **uploading an existing file**.
2. Drag in **all 7 files** from this folder.
3. Click **Commit changes**.

### Step 3 – Turn on the free hosting
1. In the repository, go to **Settings → Pages**.
2. Under **Build and deployment**:
   - **Source:** Deploy from a branch
   - **Branch:** `main`, folder `/ (root)`
3. Click **Save**.
4. Wait 1–2 minutes and refresh. GitHub shows your link: `https://<your-username>.github.io/relax/`

### Step 4 – Create the admin edit key
This key lets the app save changes to **this one repository only**.

1. On GitHub, click your **profile photo** and go to **Settings → Developer settings → Personal access tokens → Fine-grained tokens**.
2. Click **Generate new token** and fill it in:
   - **Token name:** `RelaX edit key`
   - **Expiration:** pick a date up to a year away and set yourself a reminder to renew it.
   - **Repository access:** **Only select repositories**, then choose `relax`.
   - **Permissions → Repository permissions → Contents:** **Read and write**. Leave everything else as it is.
3. Click **Generate token** and **copy** the key. It starts with `github_pat_`, and GitHub shows it only once.
4. Keep it private:
   - Never paste it into the repository or any file.
   - Never post it in a chat or channel.

### Step 5 – First launch
1. Open your link on your phone.
2. The app shows **Set up your tracker**. Fill it in:
   - **Team name**
   - **Team members**, one per line
   - A **team passcode** of 8 or more characters. Make it memorable but not guessable.
   - Your **edit key** from step 4
3. Tap **Create tracker**.
4. In **Settings**:
   - Check the team list.
   - Under **Holidays**, remove the sample entries. Tap **Paste a holiday list** and paste the official list, one per line, for example:
     ```
     26/01/2027, Republic Day
     22/03/2027, Holi
     ```

> ⚠️ **Don't lose the team passcode.** It's the only way to decrypt the data and can't be recovered. You can change it later in Settings → General.

### Step 6 – Put it on the home screen
- **iPhone (Safari):** open the link, tap **Share**, then **Add to Home Screen**.
- **Android (Chrome):** open the link, tap **⋮**, then **Add to Home screen** or **Install app**.

It then opens full-screen, like a normal app.

---

## Sharing with the team

1. Send the team the **link**.
2. Send the **team passcode** separately and privately. For example, tell people in person, or send it in a different message from the link.
3. Each person:
   - opens the link,
   - enters the passcode once,
   - adds the app to their home screen.

They can view everything but can't edit.

**Adding more admins:**
1. Give them the edit key privately.
2. On their phone they open **Settings** and tap **I'm an admin – add edit key**.
3. Then they paste the key.

**Removing an admin's access:**
1. On GitHub, delete the token and create a new one (step 4).
2. Give the new key only to the admins who should keep editing.

---

## Using it day to day

The same steps are in the app under **About → How to use**.

| To… | Do this |
|---|---|
| Add leave (admins) | Tap **+**. Choose the person, type and dates, then **Save**. Half day asks for AM/PM. |
| See who's off on a day | Tap the day. |
| Edit or delete leave (admins) | Tap the day, tap **Edit** next to the person, then **Save** or **Delete**. |
| Change view | Tap **Week / Month / Year**, or swipe left/right to move between periods. |
| Filter | Use **All people ▾** and tap the type chips to show or hide types. |
| Reports | Go to the **Reports** tab and pick a range. Tap **Export summary** or **Export entries** for files that open in Excel. |
| Get the latest changes | Reopen the app or tap **⟳** at the top. |

**How the "people off" number works:**
- Leave counts as 1.
- Half day and Summer Hours count as ½.
- You can change how each type counts in **Settings → Leave types**.

---

## Good to know

- **Backups and history:** every save is a new version in the repository's history (**Commits**), so nothing is ever lost.
- **Two admins saving at once:** the app re-reads the latest data and applies your change on top of it. Neither change is overwritten.
- **No signal:** the app opens with the last data it downloaded. Saving needs a connection.
- **Edit key expired:** the app tells you. Create a new key (step 4) and add it again in Settings.
- **Changing the team passcode:** go to **Settings → General → Change team passcode**. Everyone is asked for the new one the next time they open the app.
- **Updating the app later:** upload the new `index.html` to the repository and replace the old one. Your data isn't touched.
- **Company data:** this holds colleagues' names and leave dates outside WBD systems. Make sure your team and manager are comfortable with that. You can use first names or initials only.

---

*RelaX v1.2.0 · Designed & built by Jaydeep Saha, Senior, Photo Editorial.*
