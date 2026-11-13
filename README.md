# Promo Organiser

If you run a music channel, label or radio show, your inbox fills up with promos: label and promo-platform
mailouts, weekly digests, reminders, SoundCloud and Facebook message notifications, and artists sending tracks
directly. Promo Organiser is a Windows app that reads those mailboxes for you (Gmail and most other email services). It sorts every email, turns
the promos into one tidy list of releases, and lets you track each one from "new" to "uploaded".

- **Everything sorted into four views.** Promos, Messages (SoundCloud, Facebook and similar), Direct (personal
  emails from artists and labels) and Other (newsletters and anything the app wasn't sure about). Nothing is
  ever hidden or thrown away.
- **One release per promo.** Artist, title, label, catalogue number, release date and the promo link are read
  from FATdrop and Label Engine emails, including each entry in a weekly digest. Reminders, digests and the
  same promo arriving in several mailboxes all land on the same release instead of piling up as duplicates.
- **A workflow for each release.** New, Listened, Shortlisted, Scheduled, Uploaded or Rejected, with a tab for
  each and keyboard shortcuts to move releases between them.
- **Spot problems at a glance.**
  - ⏳ marks releases that aren't out yet, so you don't upload too early.
  - ⚑ marks release dates that look wrong, for example when two emails disagree.
  - ⚠ marks promos with missing details.
- **Your notes and permissions.** Keep notes on each release and record who gave you permission to upload it,
  and when.
- **Several mailboxes at once.** Gmail, Yahoo, iCloud, AOL, Fastmail, Zoho or any other IMAP mailbox (not
  Outlook or Hotmail yet). A problem with one mailbox never stops the others.
- **Safe with your mail.** Mailboxes are opened read-only: the app never deletes, moves, labels or marks
  anything as read. Emails are shown as plain text; images and tracking pixels are never loaded. Passwords
  are kept in Windows Credential Manager, never in a file.

## Install

Download from the [latest release](https://github.com/geodnb/promo-organiser-releases/releases/latest). There
are two ways to run it; pick one:

| Download | What it is | Updates |
| --- | --- | --- |
| `PromoOrganiser-<version>-Setup.exe` (about 6 MB) | **Installer.** Adds Promo Organiser to the Start menu and to Settings › Apps, so you can uninstall it. Installs for your account with no admin rights, or for everyone. If the .NET 10 Desktop Runtime isn't on the PC, it offers to download it from Microsoft and install it. | Built in: Settings › About & updates › **Download and install** |
| `PromoOrganiser-<version>-Standalone.exe` (about 67 MB) | **Standalone app.** One file, nothing to install, .NET included. Put it anywhere (Desktop, a USB stick) and double-click it. The first start takes a few seconds longer. | By hand: download the new `.exe` and use it instead of the old one |

Both keep your data in the same place (`%LOCALAPPDATA%\PromoOrganiser`), so you can switch between them, update
or uninstall without losing anything.

Neither file is code-signed, so the first time you run one, Windows SmartScreen may say it "protected your
PC": click **More info**, then **Run anyway**.

## Add a mailbox

Click **Add mailbox** at the top of the main window. The form has two tabs: **Gmail**, and **Other email
service** (below).

### Gmail

Promo Organiser reads Gmail over IMAP using a Google **app password**: a separate 16-character password just
for this app, which you can revoke at any time. Your normal Google password is never used.

1. **Create an app password.** Your Google account needs 2-Step Verification turned on. Go to
   [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords), enter a name such as
   "Promo Organiser", and click **Create**. Copy the 16-character password it shows.
   - **Passkeys:** if you sign in to Google with a passkey, that's fine; you still create an app password the
     same way.
   - **No app passwords option?** Google doesn't offer app passwords for work or school accounts, for accounts
     in Advanced Protection, or when 2-Step Verification uses only security keys.
   - **Changed your Google password?** Google deletes your app passwords when you do. Create a new one and
     update the mailbox in Settings › Mailboxes.
2. **Add it in the app.** Click **Add mailbox** at the top of the main window. You can also use Settings ›
   Mailboxes › **Add…**. The form's **Get an app password from Google…** button opens step 1's page.
   - **Display name:** a short name shown in the app, for example "Channel".
   - **Gmail address.**
   - **Google app password**, from step 1.
   - **Folder:** leave it as `INBOX`. Choose `[Gmail]/All Mail` instead if Gmail filters skip the inbox for your
     promos (this also reads mail you sent, which goes to Other).
3. Click **Test connection**. It should say it connected. Then click **Save**.
4. The app starts fetching straight away. The first time, it imports the last 90 days of mail; after that,
   **Refresh** (or **F5**) fetches only new mail.

### Other email services

On the **Other email service** tab, choose your service: Yahoo Mail, iCloud Mail, AOL Mail, Fastmail, Zoho Mail,
or **Other** for any other IMAP mailbox, such as your own domain's email. The server settings fill in for you.
For Other, your provider or web host can tell you the IMAP server name; the port is usually 993 with SSL/TLS.
Then fill in the display name, email address and password, and click **Test connection** and **Save**, as for
Gmail.

- **App passwords.** Most services need an **app password** here, not your normal password. The form says
  which, and where to create one.
- **Encryption:** the app only connects with encryption (SSL/TLS or STARTTLS), never without.
- **Outlook.com, Hotmail and Microsoft 365 aren't supported yet.** Microsoft no longer accepts passwords or app
  passwords for IMAP; it needs Microsoft's own sign-in.

### Afterwards

Repeat for each account. You can edit, test, disable or remove a mailbox in Settings › Mailboxes at any time;
removing one deletes its saved password but keeps the mail already imported.

## How to use it

- **Refresh (F5)** fetches new mail from every mailbox. It also runs when the app starts.
- **Promos.** Your releases, one row each, in tabs by status.
  - **Find releases:** click a column heading to sort. Narrow the list with the search box and the Label,
    Artist, Platform and Mailbox filters.
  - **Open promo** (Ctrl+O, or double-click) opens the promo link in your browser. If the promo came to more
    than one mailbox, you choose which mailbox's link to open (links are personal to each account).
  - **Ctrl+1 to Ctrl+6** move the selected releases to New, Listened, Shortlisted, Scheduled, Uploaded or
    Rejected. Right-click the list for the same options.
  - **The panel on the right** shows the selected release. Click into it and it widens. Edit any field, add
    notes or permission details, then **Save changes**.
  - **Release dates:** if a date is flagged ⚑, the panel says why. Fix it, or click **The date is right**.
    "Dates to check" above the list shows only flagged ones.
- **Messages, Direct and Other.** One email per row.
  - **Read an email:** select it to read it as plain text.
  - **Open a link:** use **Open conversation** or **Open link**. For Direct emails, any Google Drive, Dropbox
    or WeTransfer links are listed for you.
  - **Done with an email:** **Mark handled** (Dismiss in Other) ticks it off. "Hide handled" hides the ones
    you've dealt with.
  - **Create release from this** turns a message or direct email into a release.
- **Wrong category?** Use **Move to ▾**. The app remembers the sender, so their future mail goes to the same
  place, and offers to move their earlier emails too. Promo platforms are the exception: they send for many
  labels from one address. Manage these rules, or add your own, in Settings › Sender rules.
- **Add promo** adds music that reached you outside email.
- **Settings** also has:
  - **Label spellings:** treat "Example Recs" and "Example Recordings" as one label.
  - **Artist names:** names that contain "&" but are one act.
  - **Release dates:** choose which date checks run.
  - **Appearance:** light, dark or match Windows.
  - **About & updates:** versions and the update check.
  - **Maintenance:** re-run sorting on stored mail, and open the data folder.
- The line at the bottom of the window shows the app version and the .NET version it runs on. It turns red
  when either is out of date.

## Check a download

Each download has a `.sha256` file next to it. In PowerShell:

```
Get-FileHash .\PromoOrganiser-<version>-Setup.exe -Algorithm SHA256
```

The hash should match the one in the `.sha256` file. Each download also has a `.sig` file: a release signature
that the app checks before installing an update.

## Uninstall

- **Installer version:** Windows **Settings › Apps › Installed apps › Promo Organiser › Uninstall**.
- **Standalone version:** delete the `.exe`.

Either way, your database (`%LOCALAPPDATA%\PromoOrganiser`) and the app passwords saved in Windows Credential
Manager are left in place, so reinstalling picks up where you left off. Delete them yourself if you want them
gone, and revoke the app password at
[myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords).

---

This repository holds only the downloads; the source code is kept elsewhere.
