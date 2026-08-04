# Harden.Run AI Firewall

The Harden AI Firewall is a local-first AI firewall for coding and productivity agents. If AIF is useful to you please star this repo.

## Getting Started

```sh
curl -fsSL https://aif.harden.run/install.sh | sh
```

Then:

```sh
aif configure
aif demo
aif show
aif show --tui
```

<img width="3840" height="2160" alt="aif-session" src="https://github.com/user-attachments/assets/f0169edc-f1af-4f98-8f71-67f2bf73583f" />



## Supported agents

| Agent | Coverage |
| --- | --- |
| Claude Code | native hooks, pre-execution blocking |
| Codex | native hooks, pre-execution blocking |
| Cursor (IDE + CLI) | hooks, pre-execution blocking |
| Gemini CLI | hooks, pre-execution blocking |
| Kiro | hooks for the main agent; subagent MCP calls via proxy |
| OpenClaw, Hermes | block-and-steer via a bridge process |

See more at our [trust page](https://aif.harden.run/trust.md).


## Telemetry

We never collect code, commands, file paths, prompts, or anything a secret could ride in. We collect anonymous operational counters only: version, OS/arch, adapters in use, decision/block counts. 

- `aif telemetry show` prints the exact payload before it is sent — a
  secret-safety tool inspecting its own egress.
- Opt out with one environment variable: `AIF_NO_TELEMETRY=1`.

For full schema see [trust](https://aif.harden.run/trust.md).

## Contributing

Raise an issue with this attachment

```sh
aif doctor --bundle > aif-diagnostics.txt
```

## Reporting

You can use these channels

- Email **security@harden.run**, or
- Open a private report via this repository's **Security → Report a
  vulnerability** (GitHub Security Advisories).

Include the `aif doctor --bundle` output.
