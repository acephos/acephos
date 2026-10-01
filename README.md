# Aniket Singh

I work on agent harnesses, developer tooling, and service modernization using Rust, TypeScript, and Go.

The projects below show the implementation, verification, and current limits of that work.

| Project | Evidence and scope |
|---|---|
| [acex](https://github.com/acephos/acex) | Rust terminal interface for the Herdr protocol, organized into workspace crates with protocol, state, rendering, and offline validation. A preview; consult its verification record for live/platform coverage. |
| [nixos-wsl](https://github.com/acephos/nixos-wsl) | Locked NixOS/WSL configuration, rebuild/backup automation, and restore tooling. OS locks and mutable user tools have separate reproducibility boundaries; a clean-machine restore needs its own dated evidence. |
| [workstream](https://github.com/acephos/workstream) | TypeScript CLI for durable named model sessions. Session writes are serialized, checks run explicit host commands with receipts, and 22 tests pass in CI on Node 20/22/24. The live adapter generates text. |
| [strangler-lab](https://github.com/acephos/strangler-lab) | Node-to-Go service migration lab with contract tests and gateway routing. Additional migration automation is being reviewed in [PR #1](https://github.com/acephos/strangler-lab/pull/1); it is a local lab with stated evidence limits. |

Read the [workstream reliability case study](docs/workstream-reliability.md) for a concrete failure, fix, and verification boundary.

Earlier work includes the [RBAC dashboard](https://github.com/acephos/rbac-management-dashboard), whose authorization/RLS changes are awaiting staged database verification, and [Stega-Tool](https://github.com/acephos/Stega-Tool), an educational concealment exercise with persisted-file round-trip tests. Browser exercises and coursework remain learning history. Imported research and starter snapshots retain upstream attribution.

I prefer durable state, explicit authorization, failure recovery, and test results that support the claims made about a project. Repository source and test history are the evidence; private operational assets and employer work are outside this public showcase.

[GitHub](https://github.com/acephos) · [LinkedIn](https://www.linkedin.com/in/acephos)
