# Fry Word Check

A quick check of the first 300 Fry words for K–2 students, in sets of 25, with printable practice cards.

**Use it here:** https://heathmck-a11y.github.io/fry-word-assessment-and-cards/

## What it does

- The adult enters the student's name and picks a set of 25 words (1–25 through 276–300). Each set is its own finished check.
- When a name the app knows is typed, it marks the sets that student has finished and picks the next one.
- After a set, **Next set** starts the following 25 words for the same student.
- Saved checks are grouped by student, with each student's progress through all 12 sets and their scores.
- Words show one at a time on an index card. The adult taps **Yes** or **No**. The buttons are small and plain so the student can't tell which was tapped. On a laptop, the Y and N keys work too.
- The results show the score, the "not yet" words, and every word checked.
- **Download cards (PDF)** prints the "not yet" words as 2.5 × 1 inch cards, 30 to a page with cut lines. Print at 100% (actual size).
- **Retest** on a saved check gives that student only the words they missed last time and shows both scores.

## Where the data is kept

- **Every finished check saves in the browser on that device.** No sign-in or setup is needed.
- Browser data can be lost if browsing data is cleared, if the teacher switches devices, or on school Chromebooks that clear data at sign-out. The app shows a reminder when checks haven't been backed up.
- **Back up to my Google Drive** saves each check as a Google Sheet in a "Fry Word Assessments" folder in the teacher's own Drive, plus one restore file. **Restore from my Google Drive** brings the checks back on a new device. The app can only see files it created, not the rest of the teacher's Drive.
- **Download backup file** saves everything as one file without Google. **Load backup file** brings it back.

No data is ever sent anywhere else. Student results stay in the teacher's browser and, if they choose, their own Google Drive.

## Turning on GitHub Pages (one time)

1. In this repo on GitHub, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose the **main** branch and the **/ (root)** folder, then click **Save**.
4. After a minute or two, the app is live at the link at the top of this page.

## Turning on Google Drive backup (one time, about 15 minutes)

The app works without this. These steps only turn on the two Google Drive buttons.

1. Go to https://console.cloud.google.com and sign in with the Google account you want to own the app.
2. Create a new project, for example "Fry Word Check".
3. In the search bar, find **Google Drive API** and click **Enable**.
4. Go to **Google Auth Platform** (also listed as **OAuth consent screen**) and click **Get started**:
   - App name: Fry Word Check. User support email: your email.
   - Audience: **External** if teachers use different Google accounts, or **Internal** if everyone is in the same school Google Workspace.
   - Contact email: your email. Agree and create.
5. Under **Data access**, click **Add or remove scopes**, check `.../auth/drive.file` ("See, edit, create, and delete only the specific Google Drive files you use with this app"), and save.
6. Under **Audience**, if you chose External, click **Publish app** so anyone can sign in. The drive.file permission doesn't need Google's review.
7. Under **Clients**, click **Create client**:
   - Application type: **Web application**.
   - Authorized JavaScript origins: `https://heathmck-a11y.github.io`
   - Click **Create** and copy the **Client ID** (it ends in `.apps.googleusercontent.com`).
8. In this repo, open **config.js**, click the pencil to edit, paste the Client ID between the quotes, and commit.

If teachers use school Google accounts, the district's Google Workspace admin may need to allow the app before they can sign in.

## Word list

Words 1–300 follow Fry's Instant Words in the classic order and word forms (for example "following, turned, asked"). Some newer printings use base forms instead ("follow, turn, ask"). To change a word, edit the `FRY` list near the top of the script in `index.html`.

## Files

- `index.html`: the whole app.
- `config.js`: the Google Client ID setting.
