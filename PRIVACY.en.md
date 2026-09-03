# PCSSAK AroDamA Free Early Access Privacy Notice

- Document version: 1.0
- Last updated: 2026-09-01
- Applies to: PCSSAK AroDamA Free Early Access for Windows
- Operator display name: PCSSAK
- Privacy contact: `privacy@pcssak.com`
- General support: `support@pcssak.com`

> This is an English reference translation of the Korean controlling text. If translations differ,
> the Korean text controls only to the extent permitted by applicable law. Mandatory privacy and
> consumer-protection laws, and other non-waivable rights in the user's place of residence, prevail.
> This notice has not yet received professional legal review for every jurisdiction, is a conservative
> operational draft, and is not legal advice.

## 1. Processing principles and first-run consent

PCSSAK AroDamA is a local-first Windows application. The current Free Early Access has no account,
advertising, usage analytics, cloud synchronization, remote crash reporting, payment, or remote license
validation. Clipboard records and settings are managed on the user's PC. Limited network access for
update checks, user-approved downloads, and WebView2 preparation is described in Section 6.

On first launch, clipboard capture and automatic update checks remain paused until the user can open
and review the EULA and this notice in the app, select the document-confirmation checkbox, and explicitly
press the start button. The app then stores completion and capture resumption together. Local settings
record the accepted EULA and privacy-notice versions, the document-set fingerprint, and local acceptance
time; no acceptance record is sent to an account or server. A material change to license or processing
raises the document version and pauses capture pending renewed review. The installer presents the same
EULA.

## 2. Data processed when features are used

| Category | Examples | Purpose |
|---|---|---|
| Clipboard content | Text, HTML/RTF formatting, images, physical-file path lists, and virtual-file names and bytes supplied in memory | History, search, preview, and reuse |
| Source and target | Clipboard-owner process name and, only after opt-in, the automatic-paste target executable name | Search, source display, exclusions, and dated memory timeline |
| Quick text | User-created name and body | Reuse of repeated text |
| Memory organization | User-requested OCR text, tags, board names and membership, image thumbnails, and paste-queue order | Image-text search, classification, and ordered reuse |
| Portable backup | Encrypted file that may contain active and deleted records, quick text, events, OCR, and organization data as of export | Recovery or transfer to another PC |
| Settings | Hotkeys, theme, language, retention limits, excluded apps, pause state, image/file capture, and first-run completion | Preserve user preferences |
| Operational metadata | Item/event identifiers, type, start/completion times, result, count, provenance, paste method, size, pin state, and deduplication value | Sorting, timeline, integrity, retention, and deduplication |

The `{clipboard}` quick-text variable reads current Windows text only when previewed or used. That
explicit read does not by itself add a history record and is refused above the configured text limit.

Remembering automatic-paste target apps is off by default. If enabled, AroDamA stores only the executable
base name (for example, `notepad.exe`), not a document or window title, full path, PID, or HWND. Turning
the setting off affects future events and does not delete prior names. A two-step command permanently
removes only prior target-app names from the current database while retaining dates, event types, results,
and counts; the removed name cannot be restored in the app. This does not remove clipboard source-app
names. To avoid recording a source, add the app to Excluded apps or pause capture. Exclusions and enabled
default password-manager protection also apply to future paste-target names, but changing settings does
not retrospectively inspect or delete stored data.

The optional sensitive-text blocker is off by default. If enabled, narrow local rules skip recognized
private-key blocks, recognizable access-token formats, and ordinary payment-card formats that pass a Luhn
check before storage. False positives and false negatives are possible, and existing records are neither
scanned nor deleted. Passwords, one-time codes, identity, financial, medical, or confidential work data
may therefore still be captured.

## 3. Storage, encryption, and recovery protection

New data is stored under `%LOCALAPPDATA%\PCssak\AroDamA`. Only when that location is empty may AroDamA
copy the older `%APPDATA%\ClipDeck` settings and database, without deleting the old files.

- Clipboard bodies, previews, HTML, RTF, images, physical/virtual file lists, quick-text bodies, OCR,
  tag and board names, and thumbnails in active and deleted records are protected with Windows DPAPI
  in the current-user scope and are normally decryptable only in that Windows-user context.
- Selected data must be decrypted in process memory for search, preview, paste, and backup export.
  Owned buffers are overwritten where reasonably possible after use.
- Deduplication values use HMAC-SHA-256 with a per-installation secret protected by DPAPI in
  `dedup-key.bin`. HMAC is not a substitute for content encryption.
- Full-text-search candidate filters use a separate per-installation DPAPI-protected HMAC key. They do
  not store plaintext words or bodies, but this is not fully encrypted search that hides every length
  or access pattern. Actual matches are checked by individually decrypting candidates in memory.
- Some operational metadata may remain plaintext: the current item's source app, settings and database
  structure, quick-text name, identifiers, types, times, results, counts, provenance, paste method,
  retention time, size, pin state, and organization relationships. Source or opt-in target executable
  names inside events are DPAPI-protected.
- DPAPI does not defend against malware already running as the same unlocked Windows user, screen or
  keyboard capture, memory attacks, user-authorized remote control, or physical access to an unlocked PC.

Before migration, SQLite integrity controls check the existing database. A required schema or HMAC
transition creates a consistent recovery snapshot linked by a random in-database marker and snapshot
SHA-256. An interrupted transition resumes on the next launch. A linked snapshot is deleted only after
the current database, schema, required tables and columns, key marker, and WAL state pass verification;
unlinked or unproven snapshots are not automatically removed. This is crash recovery, not an external
backup service. Do not manually move or delete either data folder before final testing with real user
data and failure/recovery scenarios.

Schema v5 had no per-event history. Migration to v6 creates only a summary at the then-last copy time
and, if an automatic-paste aggregate exists, one summary at its then-last paste time; it does not infer
past individual times, targets, methods, or results. Schema v8 links RTF, registered images, virtual files,
the source `CanUploadToCloudClipboard` state, search filters, OCR, tags, boards, and paste queues to the
same `memory_id` lifecycle.

OCR runs locally with installed Windows OCR language packs and does not upload images. Results may be
inaccurate, can be deleted by the user, and are not an official transcription.

A portable backup decrypts logical records from a consistent SQLite snapshot in the current Windows-user
context and immediately re-encrypts them with the user-entered password using Argon2id and
XChaCha20-Poly1305. The password and derived key are neither stored nor sent to a server, and memory is
overwritten where reasonably possible after the operation. PCSSAK cannot recover a forgotten password or
missing file. A backup may contain active and deleted records, quick text, events, OCR, and organization
data as of export; the user controls the security and retention of its folder, external device, or sync
service. Import validates an isolated candidate and replaces rather than merges the current database.
Restoring an older backup can reintroduce data already deleted from the current app.

## 4. Retention, deletion, and restore periods

The user-defined item-count limit applies to unorganized ordinary records. Pinned records and records
linked to OCR, tags, boards, or a paste queue are protected from count-based pruning, so the actual count
may be higher. Protected and unprotected data are all subject to a separate 512 MB logical-storage cap.
Automatic count pruning bypasses the manual deleted-record store and removes linked events.

Individual deletion or Clear history moves the record and its linked events into AroDamA's local
deleted-record lifecycle, not the Windows Recycle Bin. Date-range deletion includes both endpoints based
on the record's local copy date and protects pinned records. A future date does not schedule deletion.

- Free restore is available until exactly 24 hours after deletion.
- After 24 hours, the current Free Early Access cannot restore the record, although its encrypted content
  and events may remain under the same Windows user on the same PC for up to 30 days from deletion. The
  current product has no Pro, payment, sale, remote-license activation, or UI that unlocks this data.
- Deleted records and events count toward the same 512 MB logical cap as records, pins, and quick text.
- The user may permanently erase deleted data earlier. Data reaching exactly 30 days is removed from the
  app database at the next deleted-store cleanup and cannot be restored by the app.

Expiry or permanent deletion removes content and linked events from the current database at application
level; it is not secure physical-media erasure. Traces may remain in SQLite free pages or WAL, retained
migration-recovery files, Windows or organization backups, disk-recovery areas, or third-party synchronized
copies. Deleting a stored target-app name likewise removes the ciphertext only from the current database
and does not overwrite separate copies.

The 24-hour restore boundary, 30-day expiry, and event times use local Windows system time. Large clock
changes may affect display, restore, and expiry decisions. The timeline is not signed by a trusted time
source and is not a tamper-proof audit log or legal evidence. The deleted-record store and portable backups
are separate; AroDamA cannot recover a lost database, backup file, or password.

A normal uninstall preserves the history and settings in `%LOCALAPPDATA%\PCssak\AroDamA`. Only if the
user explicitly selects `Delete app data` in the uninstaller does it delete AroDamA-managed settings, the
database, protection keys, migration-recovery snapshots, and verified restore candidates according to an
exact allowlist. Even then, it does not recursively delete the shared `PCssak\AroDamA` root or delete
user-exported `.arodama-backup` files, backups or rollback copies in another location, synchronized copies,
or organization-retention copies. Review and remove those copies separately if desired.

## 5. Sensitive-data minimization and user controls

AroDamA honors recognized Windows clipboard exclusions including `Clipboard Viewer Ignore`,
`ExcludeClipboardContentFromMonitorProcessing`, and `CanIncludeInClipboardHistory=0`. Not every password
manager or business app publishes these markers, so non-collection of sensitive data cannot be guaranteed.

The app preserves all three states of the Windows registered format `CanUploadToCloudClipboard`: absent,
DWORD 1 (allowed), and DWORD 0 (blocked). When republishing a stored item, AroDamA first republishes the
original state so it does not erase the source app's no-cloud-upload intent. AroDamA itself does not upload
the content and does not change synchronization settings for Windows or other apps. An abnormal length or
a value other than 0 or 1 is not assumed allowed; the capture is rejected.

Default password-manager protection is only a convenience filter that skips a new payload before reading
it when the Windows executable base name exactly matches `1password.exe`, `bitwarden.exe`, `keepass.exe`,
or `keepassxc.exe`. It is not a complete security boundary for every version, extension, broker process,
or elevated app. The sensitive-text blocker also uses narrow local rules and sends neither source text nor
blocked hashes to logs, the database, or the network. Neither control deletes prior records.

Users can pause capture, exclude apps, disable image/file capture, leave target-app memory off, delete
stored target names and records, empty the deleted-record store, lower limits, and remove local data.
When handling passwords, one-time codes, or personal data, pause capture; exclude security apps not in the
default list; use a separate Windows account and lock the screen on shared PCs; and review and delete
history regularly.

## 6. Network access and third-party processing

AroDamA does not upload clipboard content, local file names or paths, quick text, OCR images or results,
memory timelines, or portable backups to PCSSAK or the update server. After first-run consent, it may use
HTTPS to check the following official GitHub Release metadata address:

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

The app compares its current version with the response's version, release notes, download URL, and integrity
signature. It downloads an installer only after the user explicitly chooses to install an offered update.
GitHub may process standard request data such as IP address, access time, and user agent under GitHub's
privacy terms. AroDamA adds no clipboard content or usage history to the request; GitHub's policy governs
its processing location and retention.

If Microsoft Edge WebView2 Runtime is missing, the Tauri NSIS installation may download Microsoft's
WebView2 bootstrapper. This is not an AroDamA clipboard-data transfer, and Microsoft's policy applies.
If the user stores an encrypted backup in a folder managed by OneDrive or another third-party synchronization
app, that app may upload the file under its own settings and privacy policy.

Before any future account, payment, remote support, analytics, or crash-reporting feature is activated,
this notice will be updated with the actual transmitted data, purpose, retention, providers, and possible
international transfer, and consent required by applicable law will be obtained.

## 7. User rights, contact, and notice changes

Because there is no PCSSAK account or central clipboard database, PCSSAK cannot remotely retrieve, export,
correct, or delete local clipboard content for the user. Users control local data through the features in
Section 5 and the official deletion guidance.

Privacy questions: `privacy@pcssak.com`

General support: `support@pcssak.com`

Do not post vulnerability details, clipboard content, databases, credentials, or identifying logs in a
public issue. Use GitHub Private vulnerability reporting in the official public release repository.

PCSSAK is the current product and website operator display name; that label alone does not claim an
incorporated or registered business in any country. Paid sales requiring registered-seller disclosures or
separate sales terms will begin only after those details and terms are finalized and published.

When this notice changes, its date and version will change. Users will be notified before a material
expansion of data processing takes effect and will be asked for renewed consent where required.
