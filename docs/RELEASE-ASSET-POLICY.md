# Release Asset Policy

This repository stores public documentation and Issue forms. Generated installers, updater
signatures, SBOMs, reciprocal-license source archives, provenance, checksums, and updater metadata
are release assets and must not be committed to the Git tree.

## Current v0.4.1 asset set

Reviewed 2026-09-03. The general latest release is v0.4.1, published 2026-09-02. Historical
[v0.4.0](https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.0) assets and evidence
remain tied to that version; they are not replaced or relabeled as v0.4.1 results.

The current public `v0.4.1` release is non-draft, non-prerelease, selected as GitHub Latest,
and contains these 17 attached assets (GitHub-generated repository archives are not part of this set):

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

Missing, duplicate, renamed, extra, draft, or prerelease assets fail the contract.

## Publication order

1. Freeze and review the approved source, build, receipt, and publication commits.
2. Build the final x64 and x86 installer bytes through the approved clean release path.
3. Create and independently verify the same-name Tauri updater `.sig` files.
4. Regenerate the two CycloneDX SBOMs, notices, and exact MPL-2.0 corresponding-source archive.
5. Generate `BUILD-PROVENANCE.json` from final approved evidence. It must contain no secret,
   signing-key material, password, recovery package, device identifier, username, or local path.
6. Copy the exact public legal, privacy, security, support, and release-note bytes.
7. Generate `latest.json` for the exact architecture-specific installer URLs, signatures, version,
   and notes.
8. Generate `SHA256SUMS.txt` over the other 16 final assets. Do not include a stale checksum of a
   file that changed later.
9. Create the GitHub release as a draft, upload the exact set once, and verify names, sizes, hashes,
   JSON schemas, signatures, SBOMs, source archive, and cross-file consistency.
10. Publish only after approval, then anonymously re-download all 17 assets from the version-pinned
    URLs and repeat the independent checks.
11. Confirm the newly approved version is non-draft, non-prerelease GitHub Latest and that the fixed
    `releases/latest/download/latest.json` endpoint returns the exact approved updater metadata.
12. Only then update the production homepage to the verified public filenames, URLs, sizes, hashes,
    version, architecture, release date, and status.

## Immutability and regeneration

Never replace an asset under the same public version. If a published byte is wrong, stop promotion
and prepare a new version under the approved release process.

A recovery-media metadata schema change is private local operational evidence and is not itself a
public release asset. However, when its supporting supply-chain scripts, public release contract,
or publication commit changes, `BUILD-PROVENANCE.json` must be regenerated from the final commits;
`SHA256SUMS.txt` must then be regenerated because the provenance bytes changed. Installer hashes
remain unchanged only when the installer bytes are independently proven unchanged.

Private updater-key recovery metadata, storage-device evidence, passwords, keys, recovery
packages, and workstation details must never appear in this repository, public Release assets,
homepage data, logs, screenshots, or Issues.

The current repository EULA and privacy notice are byte-for-byte copies of the approved v0.4.1
assets. Updating living README, support, or contribution guidance is not permission to replace a
published release asset, alter consent text in an existing installer, or reissue old evidence.

## Repository boundary

The repository tree may contain README files, legal/support documents, installation and quality
guides, third-party notices, contribution rules, and Issue templates. It must not contain:

- `*.exe`, `*.msi`, `*.msix`, `*.sig`, or release archives;
- CycloneDX `*.cdx.json` files or MPL corresponding-source ZIP files;
- `BUILD-PROVENANCE.json`, `latest.json`, or `SHA256SUMS.txt`;
- private source, signing material, recovery packages, local paths, or secrets.

This separation prevents a repository commit or preview artifact from being mistaken for a
verified public installer.
