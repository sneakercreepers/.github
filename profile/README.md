# SneakerCreepers

Open-source security tooling that works with **whatever model you have**, small or large, local or in the cloud, and is **honest about what it did not check**.

## creep

[**creep**](https://github.com/sneakercreepers/creep) is a single Go binary that finds vulnerabilities in your own source code.

```sh
creep doctor && creep estimate && creep scan && creep why <id>
```

- **Measures your model first.** Calibration per vulnerability class picks a strategy tier (S, M or L) for the model you actually use.
- **Static analysis plus a model.** tree-sitter routes, sinks and auth (Python Flask/FastAPI, JS/TS Express), then the model reviews redacted code slices and answers in a closed schema.
- **Prompt-injection aware.** The planner only sees IDs, enums and booleans, never text from the scanned repository.
- **Privacy by code, not by config.** Secrets are redacted from the whole file before anything leaves your machine, and every model call is written to `egress.log` before a byte is sent. No telemetry.
- **Honest coverage.** Anything not evaluated is listed, and the run exits `4`, never `0`.
- **Any model.** OpenAI-compatible and Anthropic HTTP APIs, or any CLI (`claude -p`, `ollama run`, …) through a command contract with a tool canary.
- **Signed releases.** cosign signatures, SBOMs and build attestations.

| | |
|---|---|
| Status | [`v0.1.0-rc.1`](https://github.com/sneakercreepers/creep/releases/tag/v0.1.0-rc.1) pre-release; v0.2 (sandbox-verified findings, GitHub Action, `--diff`) in progress |
| Roadmap | [Project board](https://github.com/orgs/sneakercreepers/projects/1) · [v0.2 milestone](https://github.com/sneakercreepers/creep/milestone/2) |
| Docs | [Architecture](https://github.com/sneakercreepers/creep/blob/main/docs/architecture.md) · [Threat model](https://github.com/sneakercreepers/creep/blob/main/docs/threat-model.md) · [Wiki](https://github.com/sneakercreepers/creep/wiki) |
| License | Apache-2.0 |

## Get involved

- Start with [CONTRIBUTING.md](https://github.com/sneakercreepers/creep/blob/main/CONTRIBUTING.md) and the [`good first issue`](https://github.com/sneakercreepers/creep/labels/good%20first%20issue) label.
- Questions and ideas: [Discussions](https://github.com/sneakercreepers/creep/discussions).
- Found a vulnerability in creep itself? Please report it privately: [SECURITY.md](https://github.com/sneakercreepers/creep/blob/main/SECURITY.md).

Use creep only on code you own or are authorized to test.
