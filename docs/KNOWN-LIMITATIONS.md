# Known Limitations

[한국어](KNOWN-LIMITATIONS.ko.md)

This document records the boundaries of PCssak AroDamA Free Early Access `0.4.1`, reviewed
2026-09-03 against the published release notes and privacy notice. The core boundaries carried
forward from 0.4.0 are not newly executed test results. A successful
automated test is not a promise that every application, device, policy, locale, or clipboard
format will behave identically.

## Platform and distribution

- Windows 11 Home/Pro x64 is the primary support candidate. Windows 10 22H2 Home/Pro x64 and x86
  are limited compatibility candidates.
- Native ARM64, Windows S mode, Windows Server, Windows 11 x86, macOS, Linux, and Wine are not
  supported.
- The installers are not Windows Authenticode-signed. SmartScreen, Smart App Control, antivirus,
  or organization policy may warn or block them. The Tauri updater signature proves update-file
  integrity; it does not identify a Windows publisher.
- Clean-machine install, update, uninstall, reboot, sleep/resume, enterprise policy, and broad
  antivirus compatibility still require real-machine validation.

## Clipboard capture

- Text, HTML, RTF, common bitmap images, real file paths, and a bounded subset of OLE virtual files
  are supported. Application-private or undocumented clipboard formats may be ignored or reduced
  to a supported representation.
- Password-manager, protected-window, enterprise DLP, Remote Desktop, browser, Office, and
  sandboxed-application behavior varies. Sensitive-data filtering reduces risk but cannot detect
  every secret or confidential item.
- Sensitive-text blocking is off by default. Enabling it or changing excluded apps applies to future
  capture and does not scan or automatically delete existing history. Review old records separately.
- Core stored content is encrypted for the signed-in Windows user, but plaintext necessarily
  exists in process memory while AroDamA displays, indexes, copies, pastes, exports, backs up, or
  restores it. A compromised Windows account or running process is outside this boundary.
- Capture uses a finite queue and bounded payload rules. Extremely large, malformed, rapidly
  changing, delayed-rendered, or inaccessible clipboard content can be skipped rather than
  freezing the interface.
- Image preview may not reproduce every alpha, color-profile, animation, vector, or application-
  specific detail. OCR availability and accuracy depend on installed Windows language packs and
  source image quality.

## Search and organization

- Search uses encrypted candidate indexing and verification. The first search after migration,
  repair, a large import, or index rebuilding can be slower than later searches.
- Date, source, paste, and memory-timeline information describe events AroDamA observed or
  initiated on the local PC. They are not a forensic audit log, trusted clock, proof of authorship,
  or proof that another application consumed, displayed, transmitted, or saved the content.
- Automatic source-application detection can be unavailable or approximate when Windows or the
  target application does not expose a stable process identity.
- A library with many large images can use substantial disk space even when list thumbnails and
  pages are loaded on demand.

## Paste behavior

- Windows User Interface Privilege Isolation can block automatic input into an elevated or more
  privileged target. In that case AroDamA copies safely and asks the user to press `Ctrl+V`.
- `sent` or a successful input call means only that AroDamA issued the action. It does not prove the
  destination accepted, rendered, transmitted, or saved the content.
- Focus changes, secure fields, remote sessions, accessibility software, IMEs, keyboard layouts,
  and application shortcuts can change the result. Verify sensitive or destructive destinations.
- Plain-text fallback intentionally removes formatting. Some complex or private formats cannot be
  reconstructed after they are normalized.

## Deletion and retention

- User-deleted items can be restored for exactly 24 hours in this free release unless permanently
  deleted. Encrypted deleted data can remain locally for up to 30 days to support a future plan
  boundary, but `0.4.1` provides no recovery after 24 hours.
- The AroDamA recovery store is separate from the Windows Recycle Bin. Emptying either one does not
  empty the other.
- Logical deletion, database compaction, and file removal do not guarantee immediate physical
  erasure from SSD wear-leveling, filesystem journals, backups, crash dumps, memory, or storage
  snapshots.
- Automatic count/retention cleanup can remove old history without placing it in the user-deleted
  recovery store. Permanently deleted data is not recoverable through AroDamA.

## Backup and restore

- Backup passwords are never recoverable by PCSSAK. Losing the password makes that backup
  unusable.
- Restore replaces the active local dataset rather than merging records. An older backup can
  reintroduce data that was deleted later. Create and verify a separate backup first.
- Interrupted, damaged, wrong-version, wrong-password, or unauthenticated backups must fail closed;
  this does not make storage media failure impossible.
- Backup files contain sensitive user data even when encrypted. Keep the password separate and do
  not upload a backup to a public Issue.

## Product and service boundary

- `0.4.1` is a free Early Access release. It has no visible Pro purchase, payment processing,
  account, cloud clipboard synchronization, remote license activation, advertising, or analytics.
- A local maximum 30-day recovery foundation does not make 30-day recovery a purchasable or
  user-visible feature in this release.
- Automatic tests do not replace screen-reader and keyboard-only acceptance, native-speaker
  review of all eight languages, jurisdiction-specific legal review, or the full supported Windows
  and third-party-application matrix.

If a boundary causes data loss, corruption, unsafe behavior, or an incorrect security claim, stop
using the affected workflow and follow [SUPPORT.md](../SUPPORT.md) or privately report a security
issue through [SECURITY.md](../SECURITY.md).
