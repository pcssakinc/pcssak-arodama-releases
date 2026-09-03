# Third-Party Notices, SBOMs, and Corresponding Source

PCssak AroDamA is proprietary software that includes third-party components under their own
licenses. This map does not replace or modify any third-party license. The application source
remains private; providing MPL corresponding source for dependencies does not open the whole app.

## Current 0.4.2 compliance assets — prepared 2026-09-03

Use the [v0.4.2 release](https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.2)
for its two `PCSSAK-AroDamA_0.4.2_*.cdx.json` SBOMs,
`PCSSAK-AroDamA_0.4.2_MPL-2.0-SOURCE.zip`,
[version-pinned notices](https://github.com/pcssakinc/pcssak-arodama-releases/releases/download/v0.4.2/THIRD-PARTY-NOTICES.txt),
and `SHA256SUMS.txt`. The final release's own checksums determine identity; do not reuse a previous
release's notice, component count, or archive hash as 0.4.2 evidence. Publish these links only with
the verified 0.4.2 asset set. The repository [THIRD-PARTY-NOTICES.txt](../THIRD-PARTY-NOTICES.txt)
matches the approved 0.4.2 notice byte for byte: 465,497 bytes, SHA-256
`d22ced7c474e8de5b0dac43c86dc76bae11da91f390bac9a2b40ee6aa6bbe562`.

### Historical 0.4.1 repository notice snapshot

The preserved [0.4.1 release notice](https://github.com/pcssakinc/pcssak-arodama-releases/releases/download/v0.4.1/THIRD-PARTY-NOTICES.txt)
is 465,497 bytes, with SHA-256:

```text
86208aacae11d0e5798a34f2199dc7693b92bfcfbf84d4a9795e296c20cb82da
```

This historical identity is not the 0.4.2 notice identity or a new full provenance,
license, SBOM, or source-archive audit. Report a suspected missing attribution with the component,
version, authoritative source, and a safe description; do not upload code you lack permission to share.

## Historical 0.4.0 compliance record

The counts, names, and hash below describe 0.4.0 only. Its
[version-pinned notices](https://github.com/pcssakinc/pcssak-arodama-releases/releases/download/v0.4.0/THIRD-PARTY-NOTICES.txt)
and other assets are preserved, not overwritten or presented as fresh 0.4.2 verification.

### 0.4.0 release compliance assets

The exact version-pinned GitHub Release contains these generated compliance assets:

- `THIRD-PARTY-NOTICES.txt` — 346 recorded components and 89 deduplicated license texts;
- `PCSSAK-AroDamA_0.4.0_x64.cdx.json` — CycloneDX SBOM for
  `x86_64-pc-windows-msvc`, 344 components and a 345-node dependency section;
- `PCSSAK-AroDamA_0.4.0_x86.cdx.json` — CycloneDX SBOM for
  `i686-pc-windows-msvc`, 344 components and a 345-node dependency section;
- `PCSSAK-AroDamA_0.4.0_MPL-2.0-SOURCE.zip` — exact corresponding source selected for the
  distributed MPL-2.0 components.

These generated SBOM and source-archive assets are attached only to the version-pinned GitHub
Release. They are intentionally not committed to this public documentation repository.

### 0.4.0 MPL-2.0 corresponding-source set

The `0.4.0` compliance manifest records five distributed MPL-2.0 components and 73 corresponding-
source archive entries:

1. `cssparser-macros 0.6.1`
2. `cssparser 0.36.0`
3. `dtoa-short 0.3.5`
4. `option-ext 0.2.0`
5. `selectors 0.36.1`

The source archive must be produced from the exact locked dependency graph used by the final x64
and x86 release, independently regenerated, compared byte-for-byte or by the recorded manifest,
and published beside the binaries. Replacing a binary, dependency, toolchain input, or release
contract requires regeneration of the affected SBOM, notice, source, provenance, and checksum
assets.

### 0.4.0 explicit non-SPDX reference

Bundled SQLite `3.46.0` is explicitly represented as
`LicenseRef-SQLite-Public-Domain` with the upstream public-domain notice. This avoids silently
inventing an SPDX license identifier.

### 0.4.0 recorded notice identity

The historical 0.4.0 `THIRD-PARTY-NOTICES.txt` was recorded as 465,497 bytes with
SHA-256:

```text
ab6fb1caf57220aef31fd5bfb3390bc03bf927df342c2f471bee88f67945f55d
```

Final published SBOM and source-archive hashes belong in the same release's `SHA256SUMS.txt` and
must be verified after anonymous re-download. Do not infer a final public hash from a private
workspace, build log, or draft asset.

This document is a factual release-compliance map, not legal advice. Questions about a specific
component should use [SUPPORT.md](../SUPPORT.md); suspected missing or incorrect license material
may also be reported privately through [SECURITY.md](../SECURITY.md).
