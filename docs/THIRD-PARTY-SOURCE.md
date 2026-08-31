# Third-Party Notices, SBOMs, and Corresponding Source

PCssak AroDamA is proprietary software that includes third-party components under their own
licenses. [THIRD-PARTY-NOTICES.txt](../THIRD-PARTY-NOTICES.txt) is the public human-readable
component and license record for `0.4.0`. It does not replace or modify any third-party license.

## Release compliance assets

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

## MPL-2.0 corresponding-source set

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

## Explicit non-SPDX reference

Bundled SQLite `3.46.0` is explicitly represented as
`LicenseRef-SQLite-Public-Domain` with the upstream public-domain notice. This avoids silently
inventing an SPDX license identifier.

## Verification

The source-canonical `THIRD-PARTY-NOTICES.txt` prepared for this repository is 465,497 bytes with
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
