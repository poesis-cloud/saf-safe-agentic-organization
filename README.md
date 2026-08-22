# Poesis SAFe Agentic Organization

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-scaffold-lightgrey)](.)

> **SAFe-shaped agentic organization for GitHub Copilot / VS Code and portable agent hosts** —
> multi-agent orchestration (portfolio/program/iteration orchestrators), a framework-owned
> specialist bench, skills, instructions, workflows, artifact schemas, and deterministic model routing.
> Open-source developer tooling from [Poesis Cloud](https://poesis.cloud).

---

> **Note — v0.1:** This repository root **is** the framework application. Agents, skills, workflows,
> and the [`plugin.json`](plugin.json) manifest are its direct children — install the repository root
> as the GitHub Copilot customization plugin.

---

## The SAF solution

This repository is one of the three products of the Systemic Agentic Framework (SAF):

| Product | Repository | Role |
|---|---|---|
| Agentic Harness | [`saf-agentic-harness`](https://github.com/poesis-cloud/saf-agentic-harness) | the deterministic execution engine — methodology- and host-agnostic |
| **SAFe Agentic Organization** | **this repository** | the SAFe-shaped framework application the harness executes |
| Agentic Workspace | [`saf-agentic-workspace`](https://github.com/poesis-cloud/saf-agentic-workspace) | the shared data plane the harness checks and commits into |

The harness resolves this framework through `FRAMEWORK_DIR` and the workspace through
`FRAMEWORK_WORKSPACE_DIR` — the three products stay decoupled through environment-anchored paths,
not through a shared tree.


## Overview

The Poesis SAFe Agentic Framework brings SAFe-shaped multi-agent orchestration into
agent execution environments that support custom agents and skills. It includes:

- **Orchestrators**: `@value-management-officer`, `@release-train-engineer`, `@scrum-master`
- **Specialist bench**: framework-owned author, architecture, development, QA, security, operator, docs, and UX agents
- **Skills**: SAFe ceremony, practice, authoring, and orchestration playbooks loaded on demand
- **Model routing**: deterministic LLM tier + capability-score routing — no random model selection
- **Portable harness**: deterministic artifact, gate-packet, and runtime-trace checks independent of VS Code hooks —
  methodology- and host-agnostic, so the same familiar agentic work method follows you from host to host as you
  move between environments (shipped separately as [`saf-agentic-harness`](https://github.com/poesis-cloud/saf-agentic-harness))

## Layout

The framework is declared by [`plugin.json`](plugin.json) at the repository root and is self-contained:

- [`agents/`](agents/) — the orchestrators and the specialist bench (`<name>.agent.md`)
- [`skills/`](skills/) — SAFe ceremony, practice, authoring, and orchestration playbooks (`<name>.skill.md`)
- [`instructions/`](instructions/) — persistent conventions injected into agent sessions (`<name>.instructions.md`)
- [`conf/`](conf/) — the harness's external configuration: `workflows/`, `model-profiles`, `access-control-list`, `workspace`
- [`templates/`](templates/) — artifact Markdown templates, organized per layer and actor
- [`artifacts/`](artifacts/) — the JSON Schema contract for every artifact kind the workflows produce
- [`builds/`](builds/) — host bundle renderers (currently `github-copilot/`)

## Deterministic Harness

The framework's deterministic checks live in the sibling
[`saf-agentic-harness`](https://github.com/poesis-cloud/saf-agentic-harness) repository and run through its
stable entrypoint `harness.py`. They are host-neutral: a CI job, shell wrapper, VS Code hook, or
another agent runtime can call the same CLI. Point the harness at this repository with
`FRAMEWORK_DIR`.

Four commands (the global options `--portfolio-root`, `--strict`, `--json` come **before** the command):

```bash
# STATE — validate Epic/Feature/Story artifacts (FSM, linkage, schema, gates, derived fields)
python3 ../saf-agentic-harness/harness.py --portfolio-root /path/to/portfolio \
  check-artifact --unit-id sie-observability-foundation

# DRIVE — resolve the next orchestration action (dispatch | halt | done)
python3 ../saf-agentic-harness/harness.py \
  orchestrate --workflow value-management-officer --unit sie-observability-foundation

# CONDITIONS — evaluate one step's conditions and append the session ledger line
python3 ../saf-agentic-harness/harness.py \
  check-step --orchestration value-management-officer --step capture-epic \
  --unit-id sie-observability-foundation --session abc123

# HOOK — funnel a host lifecycle event (JSON on stdin) through the harness
cat event.json | python3 ../saf-agentic-harness/harness.py hook --event preToolUse
```

The harness never writes artifacts — it reports the value/edge; the orchestrator commits. The framework
constitution (workflow contracts + artifact catalog) is verified separately by the pytest suite:
`make -C ../saf-agentic-harness verify`.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). All contributions are accepted under Apache-2.0.
This project uses the [Developer Certificate of Origin (DCO)](https://developercertificate.org/).

---

## License

Apache License, Version 2.0. See [LICENSE](LICENSE).

Copyright 2026 Poesis Cloud and contributors.
