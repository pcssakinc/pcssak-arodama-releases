# Installation and First Run

[한국어](INSTALLATION.ko.md)

This guide applies to PCssak AroDamA Free Early Access `0.4.1`; reviewed 2026-09-03.
Older releases retain their version-pinned instructions and evidence.

## 1. Use an official release

At review, `v0.4.1` is the public, non-draft, non-prerelease GitHub Latest release with the
17 assets documented in [RELEASE-ASSET-POLICY.md](RELEASE-ASSET-POLICY.md). Verify the selected
version's files; this guide does not mark a fresh installation or signature test as passed.
A repository file, Pull Request artifact, preview deployment, source tag, work log, or unpublished
draft is not an official installer.

- Official product page: `https://pcssak.com/arodama`
- Version-pinned release:
  `https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.1`
- Fixed updater endpoint:
  `https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

## 2. Choose the correct installer

| Windows environment | Installer | Status |
| --- | --- | --- |
| Windows 11 Home/Pro x64 | `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x64-Setup.exe` | Primary support candidate |
| Windows 10 22H2 Home/Pro x64 | x64 installer | Limited compatibility candidate |
| Windows 10 22H2 Home/Pro x86 | `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x86-Setup.exe` | Limited compatibility candidate |
| Windows 11 x86 | None | Windows 11 x86 does not exist |
| Native ARM64, S mode, Server, macOS, Linux, Wine | None | Unsupported |

Windows 10 compatibility does not extend Microsoft support for Windows 10. Do not install an x86
build on a 64-bit system merely because it is available.

## 3. Verify before running

Download the installer, its same-name `.sig` file, and `SHA256SUMS.txt` from the same
version-pinned release. Compare the locally calculated SHA-256 with the published value:

```powershell
Get-FileHash -Algorithm SHA256 '.\PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x64-Setup.exe'
```

AroDamA's updater signature verifies update-file integrity with the AroDamA-specific Tauri public
key embedded in the application. It is not Windows publisher identity signing.

The `0.4.1` installers are **not Windows Authenticode-signed**. Windows may show Unknown Publisher,
Microsoft Defender SmartScreen, Smart App Control, or organization-policy warnings. Never disable
Windows Security, antivirus, a firewall, or organization policy to install AroDamA. Stop if the
filename, byte size, SHA-256, signature, version-pinned URL, or asset list does not match.

## 4. Install

1. Close an older AroDamA window if one is running.
2. Run the installer for the correct architecture.
3. Choose one of the eight installer languages.
4. Read and accept the EULA only if you agree. Cancelling must leave installation incomplete.
5. Allow Microsoft Edge WebView2 Runtime installation or delivery only when Windows needs it.
6. Start AroDamA from the Start menu or installed shortcut.

On a new 0.4.1 installation, the selected installer language is applied once to the app. An update
preserves an existing saved app language. The supported set is English, Korean, Japanese, German,
Spanish, Portuguese (Brazil), Turkish, and French. Unsupported installer languages fall back through
Windows language preferences and then English. See the [0.4.1 release notes](../RELEASE-NOTES.md).

## 5. First-run consent

Before consent, clipboard capture and automatic update checks must remain off. Review the local
data, retention, deletion, backup, update, and network explanations, then explicitly choose whether
to start capture. You can later change capture and update settings.

Core clipboard content is stored locally. Read [PRIVACY.md](../PRIVACY.md) and
[KNOWN-LIMITATIONS.md](KNOWN-LIMITATIONS.md) before using AroDamA with sensitive work.

## 6. Basic use

- Copy supported content normally; AroDamA records it while capture is enabled.
- Open the window with the configured global shortcut and search or filter by date and type.
- Press `Enter` to paste the selected item, `Shift+Enter` for plain text when applicable, or
  `Ctrl+Enter` to copy without automatic injection.
- If Windows integrity boundaries prevent automatic input, AroDamA can copy the item and instruct
  you to paste manually with `Ctrl+V`. This is expected fail-closed behavior, not proof that the
  target app accepted the data.
- Deleted items are recoverable for exactly 24 hours in this free release unless permanently
  deleted. This local recovery store is separate from the Windows Recycle Bin.

Use the [official guided examples](https://pcssak.com/arodama/guide) with synthetic text or images.
OCR is a local aid, not an authoritative transcription. Never use real passwords or customer data
for a public demonstration or issue report.

## 7. Updates

An update check is a read-only request to the fixed GitHub `latest.json` endpoint. Download and
installation require explicit user action. AroDamA does not silently install an update. If updater
metadata, signature, architecture, or release evidence is inconsistent, do not proceed.

## 8. Backup, removal, and support

A backup password cannot be recovered by PCSSAK. Restore is a replacement operation rather than a
merge and can reintroduce data contained in an older snapshot. Make a separate safe backup before
restoring or uninstalling if you need to keep history.

A normal 0.4.1 uninstall preserves history and settings. The explicit `Delete app data` option
removes only AroDamA-managed data; exported backups remain separate. Review what you want to keep
before choosing deletion. This summarizes the published release note, not a new uninstall test.

For ordinary help, follow [SUPPORT.md](../SUPPORT.md). Report security issues privately as described
in [SECURITY.md](../SECURITY.md). Do not attach real clipboard content, databases, backups,
credentials, customer data, or confidential files to a public Issue.
