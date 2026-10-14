# TH-D74 Editor v1.0.1 — D75 Testing & Reliability Update

A Windows desktop editor for Kenwood TH-D74 memories, settings, backups and guided D-STAR programming, now with an **experimental TH-D75 profile**.

## New and improved

- Automatic D74/D75 settings selection from backup headers; model-matched `.d74`/`.d75` opening, saving, discovery and connected-radio identity checks.
- Matching memory controls and **1,000 slots (000–999)** for both models, including bulk group/lockout, clear/shift, clipboard and CSV operations.
- D75-only DV Gateway, APRS Digipeater and 30-entry Hotspot List tools, plus extra display/audio/battery choices. MCP-compatible hotspot TSV import/export/template.
- Optional backup before write. With it off, ordinary writes skip the full pre-read but retain identity/protocol checks. Startup choice: last successful read, selected backup, or nothing.
- App Configuration section; filtered Log Manager with multi-select management; F10/configurable support capture with description and local ZIP. Nothing uploads automatically.
- Correct D74 microphone ordering and Detect Data label; GPS altitude editing in feet/meters with unchanged-value preservation.
- Bluetooth close-only I/O errors after a complete read are cleanup warnings, not false transfer failures. Actual transfer errors/cancellation remain intact.
- Correct app icon, transparent D75 artwork, model-aware Radio Information and wrapping support instructions.
- Filter changes reset selection after rebinding, including the native Select All range, so the next filtered list does not inherit selected rows.

Existing CHIRP CSV, multi-channel editing, compact settings, guided D-STAR, light/dark themes and the 43-site Florida SARnet stock remain included. See the README for the complete app description and changes.

## Compatibility and precautions

> **Physical TH-D75 radio read/write has not been tested here.** Selected file mappings were compared with MCP-D75, not complete compatibility certified. Preserve originals and review edited copies in MCP-D75 before considering a write.

- Windows 11 x64 is the development/testing platform. Application runtimes are bundled; radio drivers/Bluetooth setup are separate.
- Close the app before upgrading and keep an independent backup. Editing/importing does not itself write a radio.
- The final two radio-managed blocks are not written. Use matching Kenwood software for GPS receiver picture installation.
- Backup-off ordinary writes have no fresh recovery snapshot. Picture-specific uploads still read to merge only picture changes.
- Bluetooth cleanup fix passed offline checks; fresh connected-radio retesting remains necessary.

## Download

Install **TH-D74-Editor-v1.0.1-x64.msi** from the assets. `version.txt` contains `1.0.1`; `README.md` includes description, changes and instructions. No application source or private data is distributed.

MSI SHA-256: `CF716B7CC5114F9B38E002B92EF6C69E557F14D45FF5572105426809E9E77E34`

## Signing and verification

Application binaries and installer are signed/timestamped using the existing **KK4OXN self-signed development certificate**. Other PCs may still show publisher/SmartScreen warnings; this is not Microsoft certification. No security/certificate-trust settings are changed.

37 offline functional-test groups, eight protocol checks, focused D74 corrections and D74/D75 boundary tests, and 35 MCP-D75 whole-image reference comparisons passed. Installer signature/timestamp and administrative extraction integrity are checked separately. No clean-PC installation/upgrade/uninstall or physical D75 transfer is claimed.

The native UI rerun passed theme, backups, settings, D-STAR, channel selection/batch/shift, special-memory editors and grid checks. It stopped on an outdated three-section navigation assertion (the new App Configuration section makes four). That test expectation was corrected; **a full fresh UI-suite pass is not claimed.**

## Updates and feedback

[Follow KK4OXN on Patreon](https://www.patreon.com/cw/KK4OXN) for first project updates and feature requests, followed by GitHub releases. [Report bugs](https://github.com/cruzerdlc/TH-D74-Editor/issues) with model, app/Windows version, connection type and reproduction steps. Review support ZIPs before sharing; they may contain identifying information.
