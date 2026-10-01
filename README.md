# Aniket Singh

I work on agent harnesses, developer tooling, and service modernization using Rust, TypeScript, and Go.

The projects below show the implementation, verification, and current limits of that work.

| Project | Evidence and scope |
|---|---|
| [acex](https://github.com/acephos/acex) | Rust terminal control plane with a [Linux live recording and verification record](https://github.com/acephos/acex/blob/master/docs/artifacts/profile-verification-2026-10-01.md), Windows/macOS offline CI, and explicitly synthetic reducer/render timings. A source-build preview. |
| [nixos-wsl](https://github.com/acephos/nixos-wsl) | Pinned NixOS/WSL configuration with verified build receipts, locked CLI installation, and a fresh-distro evidence tool. Full system-build CI passes; [actual Windows restore evidence remains pending](https://github.com/acephos/nixos-wsl/blob/main/docs/RESTORE_EVIDENCE.md). |
| [workstream](https://github.com/acephos/workstream) | TypeScript CLI for durable named model sessions. Session writes are serialized, checks run explicit host commands with receipts, and 22 tests pass in CI on Node 20/22/24. The live adapter generates text. |
| [strangler-lab](https://github.com/acephos/strangler-lab) | Node-to-Go migration lab with 24 contract assertions, completed read-only shadow comparisons, keyed retries, and state-preserving cutover/rollback. [Merged implementation](https://github.com/acephos/strangler-lab/pull/1); read the [controlled walkthrough](docs/strangler-walkthrough.md). |

Read the [workstream reliability case study](docs/workstream-reliability.md) for a concrete failure, fix, and verification boundary.

Earlier work includes the [RBAC dashboard](https://github.com/acephos/rbac-management-dashboard), whose authorization/RLS changes are awaiting staged database verification, and [Stega-Tool](https://github.com/acephos/Stega-Tool), an educational concealment exercise with persisted-file round-trip tests. Browser exercises and coursework remain learning history. Imported research and starter snapshots retain upstream attribution.

I prefer durable state, explicit authorization, failure recovery, and test results that support the claims made about a project. Repository source and test history are the evidence; private operational assets and employer work are outside this public showcase.

[GitHub](https://github.com/acephos) · [LinkedIn](https://www.linkedin.com/in/acephos)
