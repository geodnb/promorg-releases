# Promo Organiser releases

Installers for **Promo Organiser**, a Windows app that sorts promo emails (Promos, Messages, Direct, Other) and
tracks each release from New to Uploaded. This repository holds only the installers; the source code is kept
elsewhere.

## Install

1. Open the [latest release](https://github.com/geodnb/promo-organiser-releases/releases/latest) and download
   `PromoOrganiser-<version>-Setup.exe`.
2. Run it. It installs for your user account, with no admin rights needed, or for everyone if you choose.
3. If the .NET 10 Desktop Runtime isn't on the PC, tick the option to download and install it from Microsoft.

The installer isn't code-signed, so Windows SmartScreen may say it "protected your PC". Click **More info**, then
**Run anyway**.

Needs 64-bit Windows 10 (version 1607 or later) or Windows 11.

## Check a download

Each installer has a `.sha256` file next to it. In PowerShell:

```
Get-FileHash .\PromoOrganiser-<version>-Setup.exe -Algorithm SHA256
```

The hash should match the one in the `.sha256` file.

## Updates

In the app, **Settings › About & updates › Check for updates** looks for a newer release here. **Download and
install** downloads the installer, checks it against its `.sha256`, then runs it. Your mail, releases and settings
are kept.

## Uninstall

Windows **Settings › Apps › Installed apps › Promo Organiser › Uninstall**. Your database
(`%LOCALAPPDATA%\PromoOrganiser`) and the app passwords saved in Windows Credential Manager are left in place.
Delete them yourself if you want them gone.
