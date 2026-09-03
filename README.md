# PCssak AroDamA Releases

[한국어 안내](README.ko.md)

> This repository is the public release, documentation, verification, support, and feedback home
> for PCssak AroDamA. The proprietary application source is maintained separately in a private
> repository.

PCssak AroDamA is a local-first Windows clipboard tool for finding and safely reusing text,
formatted text, images, physical or constrained virtual files, and frequently used phrases.
The current release is **0.4.1 Free Early Access**, published on 2026-09-02 (UTC).
Version 0.4.0 was the first free release; 0.4.1 retains its core features and improves installer
language handoff and update reliability. It contains no account, advertising,
analytics, payment, remote-license activation, or user-visible Pro functionality.

Free Early Access describes the maturity and current price of this version. It is not a promise
that every future version or feature will remain free.

## Development and responsibility

PCSSAK is an independent, AI-assisted development project. AroDamA addresses a practical problem:
finding something copied earlier and reusing it without losing the current workflow. Its local
history, explicit reuse, and recovery controls reflect that goal. Clipboard managers are an existing
product category; we do not claim to have invented every feature or independently authored every
component. Third-party rights remain documented separately.

AI assistance does not replace PCSSAK's responsibility for design, review, testing, release
decisions, and maintenance. We distinguish verified results from remaining limitations. This is not
a claim of an independent security audit, completed rights review, or error-free operation.

## Official download and update endpoint

Use the version-pinned official release or PCSSAK download page below. Current-document review:
2026-09-03. Historical releases keep their own documents and evidence; a later latest release does
not make an older official release unofficial.

- GitHub release: `https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.1`
- Product page: `https://pcssak.com/arodama`
- Static updater endpoint:
  `https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

At this review, `v0.4.1` is the published, non-draft, non-prerelease GitHub Latest release with the
17 named assets below. Compare exact filenames and hashes with that release. The document review
is not a new installer execution or signature-verification result. Repository files, pull-request artifacts, branch previews, source tags, work logs, and
unpublished draft assets are not public installers.

The two installer names are fixed:

- `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x64-Setup.exe`
- `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x86-Setup.exe`

Choose x64 for 64-bit Windows. The x86 installer is only for the limited Windows 10 22H2 x86
compatibility candidate. Windows 11 x86 does not exist, and native ARM64 is not supported.

## Verify before running

Compare the downloaded installer with `SHA256SUMS.txt` from the same version-pinned release:

```powershell
Get-FileHash -Algorithm SHA256 '.\PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x64-Setup.exe'
```

Each installer also has a matching `.sig`. AroDamA verifies updater artifacts with its embedded
AroDamA-specific Tauri public key. That signature protects update integrity; it is not a Windows
publisher identity.

The v0.4.1 installers are **not signed with Windows Authenticode**. Windows can show Unknown
Publisher, Microsoft Defender SmartScreen, Smart App Control, or organization-policy warnings.
Do not disable Windows security, antivirus, a firewall, or organization policy to install the app.
Stop if the filename, byte size, SHA-256, signature, fixed release URL, or asset set differs.

## Exact 17 release assets

The following files are attached to the version-pinned GitHub Release. Installers, signatures,
SBOMs, the MPL source archive, generated provenance, `latest.json`, and checksums are deliberately
not committed to the repository tree.

1. `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x64-Setup.exe`
2. `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x64-Setup.exe.sig`
3. `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x86-Setup.exe`
4. `PCSSAK-AroDamA-Free-Early-Access-v0.4.1-Windows-x86-Setup.exe.sig`
5. `BUILD-PROVENANCE.json`
6. `EULA.md`
7. `latest.json`
8. `LICENSE`
9. `PCSSAK-AroDamA_0.4.1_x64.cdx.json`
10. `PCSSAK-AroDamA_0.4.1_x86.cdx.json`
11. `PCSSAK-AroDamA_0.4.1_MPL-2.0-SOURCE.zip`
12. `PRIVACY.md`
13. `RELEASE-NOTES.md`
14. `SECURITY.md`
15. `SHA256SUMS.txt`
16. `SUPPORT.md`
17. `THIRD-PARTY-NOTICES.txt`

See [Release asset policy](docs/RELEASE-ASSET-POLICY.md) and
[third-party source information](docs/THIRD-PARTY-SOURCE.md).

## What AroDamA does

AroDamA can record supported clipboard text, HTML or RTF, images, physical files, and constrained
OLE virtual files. It provides date and type filters, encrypted-search candidates, pinned records,
quick phrases, local Windows OCR, tags, boards, an ordered paste queue, and a local memory timeline
for events observed or initiated by AroDamA.

User-deleted records can be restored for exactly 24 hours from deletion in this free build.
Encrypted data may remain locally for up to 30 days from deletion, but restore after 24 hours is
not available in v0.4.1. Permanent deletion remains available. This store is separate from the
Windows Recycle Bin.

Core clipboard content stays on the user's PC. Narrow network exceptions are the fixed GitHub
update check and user-approved update, required WebView2 delivery, and links or messages the user
opens. Read [Privacy](PRIVACY.md), the [English privacy reference](PRIVACY.en.md), and
[Security](SECURITY.md) before using the app with sensitive work.

### Privacy controls at a glance

This summarizes the approved [privacy notice](PRIVACY.md), not a new code or data-flow audit.

| Topic | What the current notice says |
| --- | --- |
| Content and metadata | Core clipboard content is protected with Windows-user DPAPI; some operational metadata can remain plaintext. This does not protect against malware running as the same user or plaintext in memory. |
| Capture and exclusions | Pause capture or exclude sensitive apps. Sensitive-text filtering is off by default, has false positives/negatives, and is not a complete secret detector. Changing exclusions does not erase old records. |
| Restore versus retention | User-deleted records are recoverable for 24 hours; encrypted deleted data can remain locally for up to 30 days. This is not 30-day free recovery or a 30-day limit for every active record. Permanent deletion is not guaranteed physical secure erasure. |
| Backup | Password-protected restore replaces the current dataset rather than merging it. Older backups can reintroduce deleted data; PCSSAK cannot recover a lost backup password. |
| Connections | No clipboard upload by AroDamA; documented update/WebView2 connections and user-opened links remain separate exceptions. |

Read the full notice for optional target-app recording, storage limits, deletion, and backup scope.

## Support boundary

Windows 11 Home/Pro x64 is the primary support candidate. Windows 10 22H2 Home/Pro x64 and x86 are
limited compatibility candidates; Windows 10 compatibility does not extend Microsoft's operating-
system support. Windows 11 x86, native ARM64, Windows S mode, Windows Server, macOS, Linux, and Wine
are unsupported.

Automated verification does not replace clean-device installation, upgrade, removal, sleep/resume,
real Office/browser/Explorer workflows, accessibility, every antivirus product, native-speaker
translation review, or jurisdiction-specific legal review. See [Installation](docs/INSTALLATION.md),
[Known limitations](docs/KNOWN-LIMITATIONS.md), and
[Quality and safety](docs/QUALITY-AND-SAFETY.md).

## Security, support, and legal documents

- Questions, experiences, and ideas: [Discussions](https://github.com/pcssakinc/pcssak-arodama-releases/discussions).
- Reproducible defects: [structured issue forms](https://github.com/pcssakinc/pcssak-arodama-releases/issues/new/choose).
- General support without GitHub: `support@pcssak.com`
- Privacy contact: `privacy@pcssak.com`
- Exploitable vulnerabilities: [private security report](https://github.com/pcssakinc/pcssak-arodama-releases/security/advisories/new), under [SECURITY.md](SECURITY.md); do not post details publicly or send them to general support.
- License and use terms: [LICENSE](LICENSE) and [EULA.md](EULA.md)
- Current release notes: [RELEASE-NOTES.md](RELEASE-NOTES.md)
- Feedback handling, contribution rights, and compensation boundaries: [CONTRIBUTING.md](CONTRIBUTING.md)

The root EULA and privacy notice are the approved 2026-09-01 documents distributed with 0.4.1.
Living support and contribution guidance can change without replacing the documents attached to a
published release. MPL corresponding-source assets cover those third-party components, not the
proprietary application source.

Never post clipboard bodies, databases, backup files or passwords, credentials, private keys,
personal paths, customer material, or confidential work in a public issue.
