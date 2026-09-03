# Quality and Safety

[한국어](QUALITY-AND-SAFETY.ko.md)

PCssak AroDamA is designed around a simple rule: copying one line or twenty thousand characters
should remain convenient now and retrievable later without hiding uncertainty from the user.
Free Early Access is not a claim of perfect compatibility.

## Current release and evidence boundaries — 2026-09-03

This guide applies to [v0.4.2](https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.2).
Release-preparation evidence is separated from public-asset verification and real-device acceptance.
The documentation update itself is not proof that publishing or a Windows installation succeeded.

| Evidence | Scope and status |
| --- | --- |
| 0.4.2 Rust automated suites | Recorded passing: `335/335` for Windows x64 and `335/335` for Windows x86. These are automated target suites, not clean-device installation tests. |
| 0.4.2 interface regression checks | Recorded passing: `21` checks covering copy actions, first-run completion, input-target isolation, and collection navigation. Isolated/mocked checks do not prove native Windows input behavior. |
| 0.4.2 language structure | Recorded passing: eight languages, `495` keys each, including placeholder consistency. This is not completed native-speaker review. |
| Legal and consent continuity | The existing EULA, privacy text, and consent versions are unchanged. A language/identity check is not legal certification. |
| Public release assets | The exact 17 assets, architecture, signatures, hashes, and Latest endpoint require the separate publication gate in [Release asset policy](RELEASE-ASSET-POLICY.md). |
| New installation and real in-app update | `NOT_RUN` for the 0.4.2 clean-device/native-upgrade matrix at preparation. Browser fixtures and automated tests are not substitutes. |
| Historical automated results | The 0.4.0 results below remain 0.4.0 evidence; 0.4.1 language/update improvements remain that version's history. Neither is relabeled as a new 0.4.2 pass. |
| Accessibility, translation, legal, and external security review | Broad exact-release acceptance remains pending unless separately recorded. |

For each future result, record the exact version and file hash, date, Windows build/architecture,
scenario, expected and observed result, and whether it was automated, real-device, or not run. Use
synthetic data; omit private paths and raw user logs. Link a confirmed defect to its fix and release,
and correct an inaccurate claim visibly rather than rewriting the historical result.

## Safety principles

1. **Consent before capture.** Clipboard monitoring and automatic update checks remain off until
   the user receives the relevant explanation and explicitly opts in.
2. **Local-first and data-minimized.** Core clipboard content remains on the user's PC. Network
   access is limited to documented update and user-initiated paths.
3. **Bounded work.** Capture queues, payloads, previews, image caches, virtual-file extraction,
   search candidates, and pages have finite limits so malformed or extreme input fails closed
   instead of consuming unbounded resources.
4. **Truthful outcomes.** Copying, issuing paste input, and proving that another application saved
   data are different states. AroDamA must not report the last one without evidence.
5. **Backend-enforced policy.** Retention, deletion, recovery, sensitive-item handling, update
   verification, and backup authentication are enforced below the visible interface.
6. **Recoverable transactions.** Schema migration and backup restore use validation, atomic
   replacement, and rollback boundaries; failure must preserve the last valid dataset when
   possible.
7. **Reproducible release evidence.** Architecture, source commit, build receipt, asset bytes,
   updater signatures, checksums, SBOMs, notices, and reciprocal-license source are verified as
   independent gates.

## Recorded automated evidence for 0.4.0

The prepared `0.4.0` code and release candidate recorded the following point-in-time checks:

- Rust test suites passed `316/316` on both Windows x64 and x86 targets.
- Clippy with warnings denied, rustfmt, the production front-end build, Tauri no-bundle debug
  builds, and updater-policy tests passed for both intended architectures.
- Eight application languages were checked at `474` keys per language for missing, extra,
  duplicate, empty, and placeholder-mismatch errors.
- EULA generation, legal-document fingerprints, third-party notices, CycloneDX SBOMs, and
  MPL-2.0 corresponding-source regeneration checks passed.
- The npm audit reported no known vulnerabilities at that point. RustSec reported documented
  allowed maintenance/unsound warnings; no known vulnerability affecting the selected Windows
  target graph was identified.
- x64 and x86 candidate installers and application binaries produced zero detections in a
  point-in-time Microsoft Defender custom scan.

These results apply only to the exact bytes and dependency graph they tested. A later source,
toolchain, signing, packaging, metadata, or asset change requires the affected checks and hashes
to be regenerated. A Defender result does not guarantee SmartScreen reputation, another antivirus
engine, or future definitions.

## Historical 0.4.0 release gate

The following preserves the gate used for 0.4.0. For the current version and filenames, use
[Release asset policy](RELEASE-ASSET-POLICY.md); a newer latest release does not invalidate the old
version-pinned publication.

Publication is acceptable only when all of these agree:

- the approved source, build, receipt, and publication commits;
- the final x64 and x86 installer bytes and architecture;
- the same-name Tauri updater signatures;
- `BUILD-PROVENANCE.json` without secrets or local paths;
- two CycloneDX SBOMs and the exact MPL-2.0 corresponding-source archive;
- current legal, privacy, security, support, release-note, and notice bytes;
- `SHA256SUMS.txt` covering the final 16 non-checksum assets;
- `latest.json` pointing to the exact published installers and signatures;
- a non-draft, non-prerelease `v0.4.0` GitHub Latest release with exactly 17 assets;
- anonymous re-download and independent hash/signature verification.

Generated installers, `.sig` files, SBOMs, MPL source archives, provenance, checksums, and
`latest.json` belong to the version-pinned GitHub Release, not the Git repository tree.

## Evidence not replaced by automation

The following remain real-world acceptance work unless a result for the exact public bytes is
separately recorded:

- clean Windows 11 x64 and Windows 10 22H2 x64/x86 installation, update, uninstall, reboot,
  sleep/resume, multi-monitor, scaling, and storage-pressure testing;
- broad Office, browser, Explorer, password-manager, OCR, IME, remote-session, elevated-process,
  accessibility-tool, antivirus, and enterprise-policy compatibility;
- keyboard-only and screen-reader acceptance and visual review at supported scale and language;
- native-speaker review of all eight translations;
- jurisdiction-specific legal advice, commercial terms, and professional accessibility or
  security certification;
- SmartScreen reputation and long-duration, high-volume user acceptance.

Until those checks are recorded, describe them as `NOT_RUN`, limited, or pending rather than
passed. See [KNOWN-LIMITATIONS.md](KNOWN-LIMITATIONS.md) for user-visible boundaries.

## Reporting a quality problem

Use the structured bug form with synthetic data. State the exact version, Windows build and
architecture, data type, expected result, observed result, and whether the data remained safe.
Never attach real clipboard content, databases, backups, credentials, customer data, or private
paths. Security-impacting behavior belongs in the private process described by
[SECURITY.md](../SECURITY.md).
