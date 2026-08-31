# PCSSAK AroDamA Free Early Access Privacy Notice

- Document version: 1.0
- Last updated: 2026-08-30
- Applies to: PCSSAK AroDamA 0.4.0 Free Early Access for Windows
- Operator display name: PCSSAK
- Privacy contact: `privacy@pcssak.com`
- General support: `support@pcssak.com`

This English text is a reference translation of `PRIVACY.md`. The Korean text controls to the
extent permitted by applicable law. Mandatory privacy and consumer rights in the user's location
remain unaffected.

## 1. Local-first processing

AroDamA is a local-first Windows clipboard manager. The current Free Early Access build has no
account, advertising, usage analytics, cloud synchronization, remote crash upload, payment, or
remote license validation. Clipboard records and settings are managed on the user's PC. Limited
network access for update checks, user-approved downloads, and WebView2 setup is described below.

On first launch, clipboard capture and automatic update checks stay paused until the user can review
the EULA and this notice in the app, selects the consent checkbox, and explicitly starts capture.
The installer presents the same EULA. The app stores the accepted EULA and privacy versions, the
document-set fingerprint, and local acceptance time in local settings; it does not send that consent
record to an account or server. A material change raises the notice version and pauses capture pending
renewed review.

## 2. Data processed when features are used

The app may process:

- clipboard text, HTML or RTF formatting, images, physical-file paths, and supported virtual-file
  names and bytes;
- the clipboard owner's executable name and, only when the user opts in, the automatic-paste
  target executable name;
- quick-text names and content;
- user-requested local OCR text, tag and board names and assignments, thumbnails, and paste-queue
  order;
- encrypted portable backups containing active and deleted records, quick text, events, OCR, and
  organization data;
- hotkey, theme, language, limits, excluded apps, pause state, and notice acceptance settings;
- operational metadata such as item type, size, time, counts, pin state, event result, paste mode,
  and identifiers needed for sorting, integrity, retention, and deduplication.

The `{clipboard}` quick-text variable reads the current Windows text only when previewed or used.
That explicit read does not by itself add a new history record and is refused when it exceeds the
configured text limit.

Remembering automatic-paste target apps is off by default. If enabled, the app stores only the
executable base name, not a document title, window title, PID, HWND, or full path. Turning the
setting off affects future events. A separate two-step command permanently removes previously
stored paste-target names from the current database while retaining the remaining event timeline.
It does not remove clipboard source-app names.

The optional sensitive-text blocker is off by default. When enabled, narrow local rules skip
recognized private-key blocks, recognizable access-token formats, and ordinary card-number
formats that pass a Luhn check. False positives and false negatives are possible. It does not scan
or delete old records. Passwords, one-time codes, identity, financial, medical, or confidential
work data may therefore still be captured.

## 3. Storage and protection

New data is stored under `%LOCALAPPDATA%\PCssak\AroDamA`. When that location is empty, the app may
copy an older `%APPDATA%\ClipDeck` database and settings without deleting the old files.

Clipboard bodies and previews, HTML and RTF, images, file lists, quick-text content, OCR, tag and
board names, and thumbnails are protected with Windows DPAPI in the current-user scope. Search and
paste operations necessarily decrypt selected data in process memory. A different per-installation
DPAPI-protected key is used for HMAC-SHA-256 deduplication, and another key protects hashed search
candidate filters. HMAC values are not content encryption and do not hide every length or access
pattern.

Some operational metadata may remain plaintext, including a current item's source app, a quick-text
name, item type and size, pin state, identifiers, event type and times, results, counts, provenance,
paste mode, retention times, and organization relationships. Source or opt-in target executable
names inside events are DPAPI-protected. DPAPI does not defend against malware already running as
the same unlocked Windows user, screen or keyboard capture, memory attacks, remote control allowed
by the user, or physical access to an unlocked device.

The database is checked with SQLite integrity controls before migration. Linked recovery snapshots
are kept when a migration cannot be proven complete and are removed only after the current database,
schema, key markers, and WAL state pass the required checks. This is crash recovery, not an external
backup service.

Local OCR uses installed Windows OCR language packs and does not upload the image. OCR can be wrong
and must not be treated as an official transcription. A portable export decrypts records in the
current Windows-user context and immediately re-encrypts them using the user's backup password with
Argon2id and XChaCha20-Poly1305. The password and derived key are not stored or uploaded. PCSSAK
cannot recover a forgotten password or missing backup.

## 4. Retention, deletion, and restore

The item-count limit applies to unorganized ordinary records. Pinned records and records linked to
OCR, a tag, board, or paste queue are protected from count-based pruning, so the actual count may be
higher. All protected and unprotected data remains subject to a separate 512 MB logical-storage cap.
Automatic count pruning does not use the manual deleted-record store and removes its linked events.

Manual deletion moves a record and its linked event history into AroDamA's local deleted-record
store, not the Windows Recycle Bin.

- Free restore is available until exactly 24 hours after deletion.
- After 24 hours, this Free Early Access build cannot restore the record, although its encrypted
  content and event history may remain under the same Windows user for up to 30 days from deletion.
- The user may permanently erase a deleted record earlier. Records expire at 30 days and are removed
  during the next cleanup.
- These boundaries use local Windows system time. Material clock changes can affect display,
  restore, and expiry decisions.

The timeline is not signed with a trusted time source and is not a tamper-proof audit log or legal
evidence. App-level expiry or permanent deletion removes current database records; it is not secure
physical-media erasure. SQLite free pages or WAL files, Windows backups, migration recovery files,
disk-recovery areas, organization backups, and third-party synchronized copies may persist.

Uninstalling does not necessarily delete `%LOCALAPPDATA%\PCssak\AroDamA`. To remove local data,
exit the app and follow the official data-removal instructions, then review separate backups and
synchronized copies.

## 5. Sensitive clipboard controls

AroDamA honors recognized Windows clipboard exclusions such as `Clipboard Viewer Ignore`,
`ExcludeClipboardContentFromMonitorProcessing`, and `CanIncludeInClipboardHistory=0`, but not every
application publishes them. It preserves the three states of `CanUploadToCloudClipboard` when it
re-publishes a stored item; this does not change Windows-wide or other-app synchronization settings.

The default password-manager convenience filter matches only the exact executable base names
`1password.exe`, `bitwarden.exe`, `keepass.exe`, and `keepassxc.exe`. It is not a complete security
boundary. Pause capture when handling secrets, add other security apps to Excluded apps, use a
separate locked Windows account on shared PCs, and periodically review and delete records.

## 6. Network access and third parties

AroDamA does not upload clipboard content, local file names or paths, quick text, OCR images or
results, timeline data, or portable backups to PCSSAK or the update service.

After first-run consent, it may use HTTPS to request official GitHub Release metadata at:

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

The app compares the current version with the version, release notes, download URL, and integrity
signature in that response. It downloads an installer only after the user explicitly chooses to
install an offered update. GitHub may process standard request data, such as IP address, access time,
and user agent, under GitHub's privacy terms. AroDamA does not add clipboard content or usage history
to the request.

If Microsoft Edge WebView2 Runtime is missing, the NSIS installer may download Microsoft's WebView2
bootstrapper. If the user saves an encrypted backup inside a folder managed by OneDrive or another
synchronization app, that app may upload the backup under its settings and privacy terms.

Future account, payment, analytics, remote support, or crash-reporting features will not be activated
without first updating this notice with the actual data, purpose, retention, service providers, and
possible international processing, and obtaining any consent required by applicable law.

## 7. User controls and contact

Users can pause capture, exclude apps, disable image or file capture, keep target-app memory off,
delete stored target names, review and delete records, empty the deleted-record store, lower limits,
and remove locally saved data. Because there is no PCSSAK account or central clipboard database,
PCSSAK cannot remotely retrieve, export, correct, or delete local clipboard content for the user.

Privacy questions: `privacy@pcssak.com`
General support: `support@pcssak.com`

Do not post vulnerability details, clipboard content, databases, credentials, or identifying logs in
a public issue. Use GitHub Private vulnerability reporting in the official public release repository.
PCSSAK is the current product and website operator display name; that label alone does not claim an
incorporated or registered business in a particular country. Any paid sale requiring registered-seller
disclosures will begin only after those details and separate sales terms are established and published.
