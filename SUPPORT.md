# Support

For any bug or coverage request please open an issue.
Individual local protection is free forever. No account or payment is required for support. 


## How to get help fastest

1. Read the **trust & transparency page**: <https://aif.harden.run/trust>. It
   answers most "is this expected?" questions — the complete network-call
   inventory, what is always blocked, measured coverage, fail-closed behavior,
   and the known gaps.
2. Run `aif doctor` for an on-screen health report (daemon health, install
   integrity, per-agent hook wiring, update status).
3. If you are stuck (an agent is being blocked and you cannot tell why, an
   update misbehaved, the daemon will not start), attach the bundle:

   ```sh
   aif doctor --bundle > aif-diagnostics.txt
   ```

   It is DLP-filtered and safe to attach — see the README.

## Reporting security issues

Do **not** open a public issue for a vulnerability. Instead:

- Email **security@harden.run**, or
- Use this repository's **Security → Report a vulnerability** (GitHub Security
  Advisories).

Attach the DLP-filtered `aif doctor --bundle` output.