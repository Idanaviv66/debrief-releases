# Debrief

**UAV flight log analyzer**: a desktop app for analyzing ArduPilot `.bin` (DataFlash) flight
logs on your own computer, with no browser or server.

This repository holds Debrief's releases only. Download the latest version from the
[**Releases page**](../../releases/latest).

## Features

- One tab per log, parsed in the background, so large (100 MB+) logs stay responsive
- Up to four panels per log: **Table**, **Parameters**, **Plot** and **Map**, with one playback
  bar
- Table: every message type and field, with units
- Parameters: values, defaults, ArduPilot descriptions, enum names and bitmask flags, with
  filters for "changed from default" and "changed during flight"
- Plot: synchronized plots of any field or formula (e.g. `ATT.DesRoll - ATT.Roll`), flight-mode
  bands and an exact cursor readout
- Map: the flight in 3D over terrain, coloured by flight mode or any field, replayable
- Offline maps, light and dark appearance

## Which file to download

| Platform                    | File                                      |
| --------------------------- | ----------------------------------------- |
| macOS, Apple silicon (M1+)  | `Debrief-<version>-mac-arm64.dmg`         |
| macOS, Intel                | `Debrief-<version>-mac-x64.dmg`           |
| Windows (installer)         | `Debrief-Setup-<version>-win-x64.exe`     |
| Windows (no install needed) | `Debrief-Portable-<version>-win-x64.exe`  |
| Ubuntu / Debian             | `Debrief-<version>-linux-amd64.deb`       |
| Other Linux                 | `Debrief-<version>-linux-x86_64.AppImage` |

Not sure which Mac you have? Apple menu → **About This Mac**: "Chip: Apple M…" means Apple
silicon, "Processor: Intel…" means Intel.

## Installing and opening Debrief

Debrief isn't signed with a paid Apple or Microsoft certificate yet, so the first time you open
it, macOS and Windows warn that they don't recognize the developer. The steps below get past the
warning. You only need to do this once per install.

### macOS

1. Open the `.dmg` and drag **Debrief** into **Applications**.
2. Open Debrief from Applications. macOS says it can't verify the app. Click **Done** (not
   _Move to Trash_).
3. Open **System Settings → Privacy & Security**, scroll down to the message about Debrief and
   click **Open Anyway**. Confirm with your password or Touch ID.
4. Debrief opens. From now on it opens normally.

On macOS 14 (Sonoma) and earlier, you can instead right-click (or Control-click) Debrief in
Applications, choose **Open**, then click **Open** again.

<details>
<summary>Alternative: Terminal</summary>

```bash
xattr -dr com.apple.quarantine /Applications/Debrief.app
```

This removes the "downloaded from the internet" flag from Debrief only.

</details>

### Windows

**Installer** (`Debrief-Setup-…exe`):

1. If your browser warns that the file "isn't commonly downloaded", choose **Keep** (in Edge:
   **…** → **Keep** → **Keep anyway**).
2. Run the installer. If a blue **"Windows protected your PC"** window appears, click
   **More info**, then **Run anyway**.
3. Follow the installer. Debrief is added to the Start menu.

**Portable** (`Debrief-Portable-…exe`): no installation. Put the file anywhere and double-click
it. The same **More info → Run anyway** step applies the first time.

### Linux

**Ubuntu / Debian (`.deb`)**, recommended:

```bash
sudo apt install ./Debrief-<version>-linux-amd64.deb
```

Then start Debrief from your applications menu.

**AppImage** (other distributions):

```bash
chmod +x Debrief-<version>-linux-x86_64.AppImage
./Debrief-<version>-linux-x86_64.AppImage
```

If it doesn't start, install FUSE 2 (`libfuse2`, or `libfuse2t64` on Ubuntu 24.04 and later),
or use the `.deb`.

## Updates

Debrief checks this page for a newer version when it starts and every few hours while it's open.
You can also check any time with **Check for Updates…** (in the **Debrief** menu on macOS, the
**Help** menu on Windows and Linux). When there's an update, a button appears at the top right of
the window:

- **Windows (installer) and Linux (AppImage):** Debrief downloads the update in the background
  (**Downloading update…**), then shows **Restart to Update**. Click it, or just quit Debrief, and
  the new version installs itself.
- **macOS, Windows portable and `.deb`:** the button says **Update to …** and opens the download
  page. Install the new version the same way as the first time, over the old one.

Your settings, recent files and offline maps are kept.

## Reporting a problem

Open an [issue](../../issues) with your Debrief version (**About Debrief**), your operating
system, and what happened. Please don't attach flight logs unless you're happy for them to be
public.

## License

Debrief is free to use, for any purpose, including commercial work. You may not redistribute,
modify or reverse engineer it, and it comes with no warranty. The full terms are in
[LICENSE](LICENSE); the installers show them before installing, and the app shows them under
**Help → License**.

## Attribution

Parameter and log message descriptions © ArduPilot contributors, licensed
[CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/), from
[ardupilot.org](https://ardupilot.org). Each download includes a `NOTICE` file listing every
third-party component and its license.

Debrief is not affiliated with or endorsed by the ArduPilot project.
