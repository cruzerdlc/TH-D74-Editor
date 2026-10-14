# TH-D74 Editor

![Version](https://img.shields.io/badge/version-1.0.1-blue) ![Platform](https://img.shields.io/badge/Windows_11-x64-0078D4) ![Publisher](https://img.shields.io/badge/by-KK4OXN-555555)

**A Windows desktop editor for the Kenwood TH-D74, built to make radio programming easier to understand and easier to manage—with an experimental TH-D75 profile for community testing.**

Work with your channels in a readable grid, organize several memories at once, review imports before applying them, and keep your radio images backed up. Compact settings panels and a guided D-STAR workflow put related controls together without making you hunt through separate menus.

[Download the installer](https://github.com/cruzerdlc/TH-D74-Editor/releases/latest) · [Latest updates & feature requests on Patreon](https://www.patreon.com/cw/KK4OXN) · [Report an issue](https://github.com/cruzerdlc/TH-D74-Editor/issues)

Project updates appear on **Patreon first**, followed by GitHub. Follow Patreon for the earliest announcements and testing news.

> **TH-D75 testing notice:** Selected backup settings have been compared with Kenwood MCP-D75 using isolated saved copies. **Physical TH-D75 radio read/write has not been tested here.** D75 support remains experimental—not a claim of complete compatibility. Keep an original backup and review an edited copy in MCP-D75 before attempting a radio write.

## What's new in v1.0.1

### Installer refresh — October 14, 2026

This replaces the earlier v1.0.1 installer without changing the version number. **Download the MSI again and run it to update an existing v1.0.1 installation.** The version-only update checker cannot distinguish this refresh from the earlier package.

- **USB/COM identification:** tolerates late `?`, blank and echoed command replies while waiting for the real radio identity. Wrong/unknown models are still rejected, and probing remains bounded and cancellable. An identity-only check succeeded on a connected TH-D74; a complete fresh radio transfer is not claimed.
- **Split-channel offsets:** the memory table and editor now show TX minus RX, including negative and unusual splits. The editor keeps the transmit frequency editable and the calculated offset read-only. Radio storage and CHIRP split-frequency export are unchanged.

### Model-aware D74 / D75 support

- Open `.d74` and `.d75` backups. The actual MCP/model header selects the matching profile and settings automatically; renaming a file does not convert it.
- Matching memory layouts for both models: group/search filters, Hide empty channels, Open backup, Save a copy, selection count, editing tools, and clear model/file status.
- **All 1,000 ordinary memories (000–999)** are available, including channel 999, through editing, batch operations, imports/exports, and row insertion/deletion.
- Model-matched saving and radio identity checks block D74/D75 mix-ups. Saves preserve headers and reject mismatched extensions or another model's existing destination. Raw clipboard records cannot cross models; CSV is the interchange route.
- D75-only choices include information backlighting, demodulation display, guidance speed, phonetic callsign readout, volume-linked sound levels, and charging while powered on.
- Dedicated D75 **DV Gateway**, **APRS Digipeater**, and **30-entry Hotspot List** pages. Hotspots support editing, search, multi-select removal/lockout, reordering, and MCP-compatible TSV import/export/template.
- An original snapshot is preserved before the first offline D75 edit. Save a copy protects the opened original. Model-specific radio pictures appear only in Radio Information; app branding remains consistent.

### Backups and transfers

- Enabled-by-default **backup before write** preference. Turning it off makes an ordinary Write radio a single upload pass without the previous full memory pre-read; identity and protocol checks remain.
- Exactly one startup choice: **last successful radio read**, **a selected saved backup**, or **nothing**. Backup browsing recognizes both models.
- Bluetooth/serial **close-only I/O errors are cleanup warnings**, rather than incorrectly reporting a completed, saved read as failed. Genuine transfer errors/cancellation still report normally. Fresh hardware retesting of this fix is still needed.
- Model-correct backups, separate protected last-read snapshots, and firmware metadata. Firmware is read from the radio or matching metadata, never guessed from the backup's file-format version.

### App Configuration and troubleshooting

- Dedicated **App Configuration** navigation: App Settings, Log Manager, and Submit Trouble Ticket. Project links use a wrapping horizontal footer in App Settings.
- **Log Manager:** filter app, backup-operation, read/write, error logs and support ZIPs; search, preview, save copies, and multi-select for confirmed Recycle Bin deletion. Active logs are protected.
- **F10 log capture**, with a configurable foreground-app shortcut. Capture current logs at a problem, add a description, and save a support ZIP. A GitHub issue draft can be opened, but **nothing is uploaded or submitted automatically**.
- Support instructions wrap inside their cards. RadioReference application-key controls are hidden; account username/password remain session-only. No credentials or private keys are distributed.

### D74 corrections and polish

- Correct microphone sensitivity ordering: **High / Medium / Low**.
- Correct APRS DCD code 1 label: **Detect Data**.
- Altitude editing for all five saved GPS positions, in configured feet/meters, including below-sea-level values. Unchanged values preserve exact stored meters to avoid repeated-save rounding drift.
- Correct app icon in the title/taskbar, transparent D75 artwork, model-aware dashboard information, and consistent memory-view controls.
- Selection is cleared after a filter refresh, including when Select All was used, so hidden or newly shown rows cannot inherit the previous selection.

## What you can do

| Area | Features |
| --- | --- |
| Memory channels | Edit 1,000 slots; search/filter by group; Shift/Ctrl multi-select; batch group or scan lockout changes; clear contents or delete rows and shift up. The Empty flag is hidden; empty slots remain available. |
| Everyday editing | Supported right-click cut/copy/insert/delete, above/below placement, strong selection highlighting, confirmation and Undo. Floating key hints are hidden; shortcuts remain. |
| Channel imports | Preview stock configs and CHIRP-style CSV, select rows, choose a destination/group, and review skip/overwrite behavior. CHIRP export and templates are included. |
| Florida SARnet | A bundled 43-site stock config, listed tones and +5 MHz inputs. Estero and Pahokee are excluded because the reference marks them TBD. |
| D-STAR | Guided repeater/hotspot setup, command previews, reflector/repeater tools, and routing-field spacing. It prepares memories; it does not register callsigns, provide a gateway connection or transmit automatically. |
| Other memories | Program Scan, Call, Weather, VFO, repeater and callsign tools; D75 additionally exposes its experimental hotspot list. |
| Settings | Compact Common Settings, Configuration, GPS & Digital, and APRS panels. FM Radio Mode remains separate; D75-only menus appear only for D75. |
| Backups | Open/save model-correct images; browse known folders; filter, rename, and multi-delete with confirmation. Protected snapshots cannot be deleted through the manager. |
| Appearance | Light/dark mode, one sun/moon toggle, matching title bar, collapsible navigation and lined grids sized to their content. |
| Connection | Compact COM selection/refresh, explicit read/write, progress, cancellation, model verification and optional pre-write backup. |
| Troubleshooting | Filtered log management and on-demand support ZIPs with a problem description. Files stay local until you share them. |

## Download and install

1. Download **TH-D74-Editor-v1.0.1-x64.msi** from the [v1.0.1 release](https://github.com/cruzerdlc/TH-D74-Editor/releases/tag/v1.0.1).
2. Save your work and close TH-D74 Editor before upgrading. Keep an independent radio backup.
3. Run the MSI and follow its prompts. Installation is per-machine and may request administrator approval.
4. Open **TH-D74 Editor** from the Start menu.

The installer uses `Program Files\TH-D74 Editor` and the existing upgrade family. Windows Installed apps provides repair/uninstall. Required .NET/Windows App SDK application runtimes are bundled; Python is not required. Radio drivers and Bluetooth setup are separate.

**Development/testing platform:** Windows 11 x64. Windows 10 and Windows on ARM have not been verified. Package extraction checks do not substitute for a clean-PC install/upgrade/uninstall test.

### Windows signing

The app's own executable/assemblies and MSI are SHA-256 signed and timestamped using the existing KK4OXN **self-signed development certificate**. This is not a public certificate-authority certificate or Microsoft certification.

- Subject: `CN=KK4OXN, O=RT-950 950Pro Editor`.
- Thumbprint: `ECAD9E3256B94239B01C126DB6693D153744D209`.
- Other PCs may still show unknown-publisher or SmartScreen warnings if the certificate is not trusted or the download lacks reputation.
- The installer does not disable Windows protections, add trusted certificates, or change security settings. No private signing material is included.

Only install from the project's verified release location; do not disable Windows security protections to install the app.

## Your first programming session

1. Open a matching backup or select the correct model/COM port and read your radio. Opening a backup selects its profile automatically.
2. Save an independent original backup. For D75, treat every feature as experimental and review your separately saved copy in MCP-D75 before a write.
3. Edit channels/settings or open **Channel import → Stock Configs / CHIRP CSV** and review the rows you want.
4. Confirm the destination group/placement and inspect the results. Supported changes can be undone.
5. Save using the model's correct extension. Writing a connected radio is a separate, explicit action.

For SARnet choose **Florida SARnet** in Stock Configs. It is a reference-list snapshot, not a live availability report. Check local operating requirements before transmitting.

## Important limits and safeguards

- **D75 hardware transfers have not been tested here.** MCP comparisons validate selected file mappings, not every setting or hardware behavior.
- Identity checks reject unknown/mismatched radios before memory transfer. They cannot guarantee recovery from disconnections or interrupted writes.
- The final two radio-managed blocks are not written. Use matching Kenwood software for GPS receiver picture installation. Boot-picture-specific uploads still need a fresh read to merge picture-only changes, even with pre-write backup off.
- Unsupported modes such as DMR are not silently converted to FM. Unsupported CHIRP settings are rejected instead of guessed.
- CSV is channel interchange, **not a full backup**. Groups, settings, fine tuning, power and digital fields may not transfer through other software. CHIRP export does not invent per-channel power; review destination settings and D-STAR routing.
- MARS options apply only to appropriately hardware-modified radios. The app cannot modify hardware or grant permission to transmit.
- RadioReference needs configured application access and your own appropriate premium account. Availability depends on setup; no application key or account credentials ship in this package.
- Logs may contain identifying paths/callsigns. Review support ZIPs before public sharing. Radio images, credential/settings files and older support ZIPs are excluded from capture.
- Installer/uninstaller actions do not intentionally remove personal AppData settings, stocks or backups. Keep an independent backup before updating.

## Support the project or request a feature

### [Visit KK4OXN on Patreon](https://www.patreon.com/cw/KK4OXN)

Have an idea for a stock config, a simpler workflow or another radio tool? Share the model, what you want to accomplish, and an example or screenshot. Remove passwords, API keys and private information first. Requests are welcome; feasibility and compatibility need checking before an addition can be promised.

Bug reports can also go to [GitHub Issues](https://github.com/cruzerdlc/TH-D74-Editor/issues). Include app/Windows version, model, connection type, reproduction steps and whether you used a backup or connected radio. F10 can capture logs at the problem.

## Release details

- Version: **1.0.1** (`version.txt` matches).
- Installer: **TH-D74-Editor-v1.0.1-x64.msi**.
- Publisher: **KK4OXN / Jorge De La Cruz**.
- MSI SHA-256: `AEC0CFEA9220091561930D405A3C34E71D007D262C9C3C95AC47F4A2AC1C6F10`.
- Installer/documents only: no application source, debug symbols, personal radio images/logs, credentials or private signing material.
- [Free Redistribution License](https://github.com/cruzerdlc/TH-D74-Editor/blob/main/LICENSE.md). Third-party notices are installed with the application.

### Verification scope

38 offline functional-test groups, 11 protocol checks, focused D74 corrections/altitude tests and 35 whole-image MCP-D75 reference comparisons passed for this refresh. Checks include split-offset/CHIRP preservation, identity noise, model rejection, cancellation and D74/D75 memory boundaries. The full native UI suite passed, covering themes, backups, settings, guided D-STAR, selection/batch/shift, special-memory editors, navigation, split-offset controls and grid layouts. Installer signature/timestamp and extracted payload checks are performed separately. These are not full physical-radio tests or a clean-PC installation certification. See release notes for limitations.

This independent project is not official Kenwood software or endorsed by Kenwood, Microsoft, CHIRP or SARnet.
