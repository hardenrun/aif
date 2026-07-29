# Security Policy

AIF is a local-first, pre-execution security control for AI coding agents.
We take the security of the tool — and of the developer machines it runs on —
seriously. This document tells a security researcher exactly where and how to
report an issue, and states which platforms the beta supports.

## Reporting a vulnerability

**Please report security issues privately. Do not open a public GitHub issue
for a vulnerability.**

- **Preferred:** email **security@harden.run** with a description, reproduction
  steps, affected version (`aif --version`), and platform.
- **Alternative:** open a private report via GitHub Security Advisories
  ("Report a vulnerability") on the public issue-tracker repository.

For sensitive reports, request our PGP key in your first email and we will
provide an encrypted channel. Please give us a reasonable opportunity to
investigate and fix the issue before any public disclosure; we practice
coordinated disclosure and will credit reporters who wish to be named.

### What to include

- The AIF version (`aif --version`) and OS/architecture.
- A minimal reproduction. If it involves an agent tool call, the redacted
  `aif doctor` bundle is ideal — it is DLP-filtered and never contains tool
  inputs or secrets (see the README's diagnostics section).
- Impact: what an attacker can do, and any suggested remediation.

### Response targets (best-effort, beta)

- **Acknowledgement:** within 3 business days.
- **Triage / severity assessment:** within 10 business days.
- Beta support is best-effort with **no contractual SLA** (SLAs are an
  Enterprise offering). We will keep you updated through resolution.

### Scope

In scope: the `aif` binary and daemon, the installer (`install.sh`), the
release/signing chain, the local `aif show` viewer, and the client SDKs
(`@aif/harden`, `harden-aif`).

Out of scope: findings that require a machine already fully compromised by an
attacker with local root; social-engineering of the operator; and vulnerabilities
in third-party dependencies that do not affect AIF as shipped (report those
upstream, but tell us so we can pin/patch). AIF is a defense-in-depth control:
"an agent action we do not yet block" is a coverage gap best filed as a normal
issue with a reproduction, not a vulnerability report — unless it defeats an
enforcement guarantee the trust page claims.

## Verifying what you downloaded

Every release ships a `sha256sums.txt`. When release signing is provisioned,
a detached `sha256sums.txt.minisig` (minisign / Ed25519) and macOS Developer
ID notarization authenticate origin; the installer and `aif update` refuse a
tampered or wrong-key artifact. See `runtime/install/SIGNING.md` for the
signing chain and the published public key.
