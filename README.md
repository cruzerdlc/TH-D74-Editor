# TH-D74 Editor

![Version](https://img.shields.io/badge/version-1.0.0-blue) ![Platform](https://img.shields.io/badge/Windows_11-x64-0078D4) ![Publisher](https://img.shields.io/badge/by-KK4OXN-555555)

**A Windows desktop editor for the Kenwood TH-D74, built to make radio programming easier to understand and easier to manage.**

Work with your channels in a readable grid, organize several memories at once, review imports before applying them, and keep your radio images backed up. Compact settings panels and a guided D-STAR workflow put related controls together without making you hunt through separate menus.

[Download the installer](https://github.com/cruzerdlc/TH-D74-Editor/releases/latest) · [Request a feature on Patreon](https://www.patreon.com/cw/KK4OXN) · [Report an issue](https://github.com/cruzerdlc/TH-D74-Editor/issues)

## What you can do

| Area | Features |
| --- | --- |
| Memory channels | Edit 999 memory slots; search and filter by group; use Shift/Ctrl selection; change groups or scan lockout for multiple channels; clear contents or delete rows and shift later memories up. |
| Everyday editing | Right-click commands for supported cut/copy/insert/delete operations; above/below placement choices; clear selection feedback; confirmation and Undo for supported changes. |
| Channel imports | Preview stock configurations and CHIRP-style CSV files, select individual rows, choose a destination group, and review skip/overwrite behavior before committing. CHIRP export and an example template are included. |
| Florida SARnet | A bundled **43-site Florida SARnet** stock config from the supplied reference list, with +5 MHz repeater inputs and the listed access tones. Estero and Pahokee are excluded because they are marked TBD. |
| D-STAR | Guided repeater/hotspot setup, readable command previews, reflector/repeater tools, and automatic routing-field spacing. Registration and gateway permissions are not automated. |
| Other memories | Grid views and supported editors for Program Scan, Call Channel, Weather, VFO, repeater lists, and callsign lists. Weather defaults and view-column controls are available. |
| Radio settings | Consolidated Common Settings, Configuration, GPS & Digital, and APRS panels; FM Radio Mode remains separate. |
| Backups | Open/save `.d74` radio images; browse known backup folders; filter, rename, and select multiple backups for confirmed deletion. Protected snapshots cannot be deleted through the manager. |
| Appearance | Light/dark mode, a sun/moon toggle, a matching title bar, collapsible navigation, and lined grids with readable headings. |
| Radio connection | COM-port selection, refresh, read/write controls, progress, and cancellation in the Radio Information area. |

## Download and install

1. Download **TH-D74-Editor-v1.0.0-x64.msi** from the release assets.
2. Save your work and close TH-D74 Editor before installing or upgrading.
3. Run the MSI and follow its installer prompts. Installation is per-machine and may ask for administrator approval.
4. Open **TH-D74 Editor** from the Start menu.

The installer places the application under `Program Files\TH-D74 Editor`. Normal MSI repair/uninstall is available through Windows Installed apps. The package contains the application and its required .NET/Windows App SDK files; Python is not required. A radio's USB/serial driver is separate and is not installed by this MSI.

**Verified platform:** Windows 11 on an x64 PC. This release has not been verified on Windows 10 or Windows on ARM.

### A note about Windows signing warnings

The app's own executable/assemblies and the MSI are SHA-256 code-signed and timestamped with the existing KK4OXN **self-signed development certificate**. It is not a public certificate-authority certificate and it is not Microsoft certification.

- Certificate subject: `CN=KK4OXN, O=RT-950 950Pro Editor` (the same signing identity used for the earlier app).
- Certificate thumbprint: `ECAD9E3256B94239B01C126DB6693D153744D209`.
- On PCs that do not already trust this certificate, Windows can still show an unknown-publisher or SmartScreen warning.
- The MSI does **not** disable SmartScreen, add trusted roots/publishers, or change Windows certificate trust settings.
- Private signing keys and certificate-password files are **not** included.

Only install files from the publisher's verified release location. Do not disable Windows security protections to install this app. [Microsoft explains how signing and SmartScreen reputation differ](https://learn.microsoft.com/en-us/windows/apps/package-and-deploy/smartscreen-reputation).

## Your first programming session

1. Open an existing `.d74` backup, or select the correct COM port and read the radio.
2. Save a backup before making changes. Keep it somewhere separate from the application folder.
3. Edit channels/settings, or open **Channel import → Stock Configs** / **CHIRP CSV** and review the rows you want.
4. Choose the destination group and placement. Confirm the import, then check the resulting memories.
5. Save the edited image. Writing the radio is a separate, explicit action—previewing or importing a CSV does not transmit or write to the radio.

For SARnet, select **Florida SARnet** in Stock Configs. The supplied image's TX frequencies are repeater outputs: the radio receives there and transmits 5 MHz higher. This stock is a reference-list snapshot, not a live system-status report. [SARnet's map explains the offset](https://sarnetfl.org/uploads/6/1/7/0/61701057/20230910_sarnet_map.pdf).

## Important limits

- Use the profile that matches your radio. Capability checks do not grant permission to transmit or change radio hardware capability.
- Unsupported digital modes such as DMR are not converted to FM. CHIRP rows using unverified reversed-DCS, priority-scan, or per-channel transmit-disable settings are blocked rather than silently changed.
- A CSV is a channel-interchange file, **not a full radio backup**. Radio-specific group/settings information, fine-mode details, per-channel power, and some digital information may not transfer through other software. Power is omitted from CHIRP exports rather than invented; review the destination radio's power settings.
- D-STAR routing fields should be verified in the destination software; some CHIRP versions do not retain them from generic CSV.
- RadioReference searches require your own approved application key and appropriate RadioReference account access. No account credentials or application keys ship in this release.
- The installer/uninstaller does not intentionally remove your personal AppData settings, stock configurations, or backup images. Always keep an independent backup before an update.

## Support the project or request something new

Have an idea for a feature, a stock configuration, an easier workflow, or another radio tool?

### [Visit KK4OXN on Patreon](https://www.patreon.com/cw/KK4OXN)

Tell me the radio model, what you want to do, and what would make it easier. Screenshots and small sample files help explain import formats—please remove passwords, API keys, and other private information first. Requests are welcome, but compatibility and feasibility need to be checked before an addition can be promised.

Bug reports can also go to [GitHub Issues](https://github.com/cruzerdlc/TH-D74-Editor/issues). Include the app version, Windows version, steps to reproduce, and whether you were working from a backup or connected radio.

## Release details

- Version: **1.0.0** (`version.txt` contains the same version).
- Installer: **TH-D74-Editor-v1.0.0-x64.msi**.
- Publisher: **KK4OXN**.
- MSI SHA-256: `AD1064D1400861E73D6A8EC16C532C575F49D3931044AF04A008D28E74EA67DB`.
- Distribution: installer and release documents only; no application source, debug symbols, personal backups, or private signing material are included in the upload packages.

### Verification scope

The 35 offline functional-test groups and six protocol tests passed. The MSI's administrative extraction and installed-file integrity checks were also performed; this does not claim a normal install/upgrade/uninstall was tested on a separate clean PC. No connected-radio write was performed during release verification. The complete screen-automation suite encountered intermittent dialog-timing failures, so this release is not represented as having a fresh complete UI-suite pass.

This is an independent project, not official Kenwood software or an endorsement by Kenwood, Microsoft, CHIRP, or SARnet. Third-party notices are installed with the application.
