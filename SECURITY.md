# Security policy

## Supported version

Security fixes are applied to the latest release on the default branch. The supported series is `1.x`.

## Threat model

Treat every source material, uploaded venue template, LaTeX project, document, data file, PDF, and ZIP as untrusted. The workflow rejects path traversal, unsafe names and symlinks, duplicate or oversized archive parts, macros, active Word fields, altChunk imports, external package relationships, unresolved revisions, non-flat source archives, nonportable package paths, unbounded subprocess output, stale build evidence, and source-free publication structures. Intake copies bytes and never intentionally executes source scripts, macros, OLE objects, notebooks, or embedded packages.

Word/LibreOffice and TeX/PDF parsers remain third-party attack surfaces. Perform source rendering only after preflight, with macros and link updates disabled, preferably offline or in an isolated account/container. `--no-shell-escape` is not a filesystem sandbox; Tectonic `--untrusted` is preferred, and sensitive projects should still be built in an OS-level sandbox.

## Reporting a vulnerability

Use this repository's [private security-advisory form](https://github.com/howardtuan/Hackathon-T096-Anything-to-Journal/security/advisories/new). Do not publish a weaponized sample or attach real user materials to a public issue. Provide a minimal synthetic reproducer, affected version/commit, expected behavior, and impact. Remove unpublished research, personal data, access tokens, and third-party copyrighted content.
