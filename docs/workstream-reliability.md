# Making workstream completion checks reviewable

Workstream stores named model conversations in local JSON files. Its initial implementation could read the same snapshot for two concurrent sends and overwrite a turn. It also used `Promise.withResolvers` while advertising Node 20 support, and delivery checks accepted phrases in an assistant transcript as completion evidence.

[PR #1](https://github.com/acephos/workstream/pull/1) serializes whole mutations with a local filesystem lock and writes unique atomic snapshots. Failed adapter calls preserve their user turn and error. Corrupt sessions surface explicitly, and abandoned locks require deliberate recovery rather than silent expiry.

Delivery criteria now accept hashed file artifacts or explicitly enabled host command argv. A criteria line such as `command:["npm","test"]` runs only when the caller enables host checks. Receipts record arguments, timestamps, exit status, timeout, and hashes of criteria/output. Text claims, missing criteria, and empty criteria fail closed. File presence proves presence; a command proves only what that command tests.

The live HTTP adapter has a timeout and accepts cancellation. Command timeouts terminate the process tree. Node 20 compatibility uses supported timer/promise APIs.

The merged revision passed 22 tests and type checking in GitHub CI on Node 20, 22, and 24. The regressions cover overlapping harness instances, duplicate creation, failure recovery, forged transcript evidence, command failure/timeout, corrupt state, and HTTP cancellation.

This remains a model-session MVP. It does not execute model tool calls or autonomously supervise code-editing workers. Locks assume a local filesystem, and an injected adapter must cooperate with cancellation. Those limits are part of the product's current contract, rather than implied production/adoption evidence.
