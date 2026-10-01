# A controlled service migration, with evidence

The original strangler-lab prototype could count any shadow response as a match and switch to an independent empty store. Passing those gates did not establish data continuity. [The merged repair](https://github.com/acephos/strangler-lab/pull/1) compares primary/candidate status and bodies, mirrors reads only, and transfers active state before changing routes.

Run with Go 1.22+ and Node 22+:

```bash
git clone https://github.com/acephos/strangler-lab.git
cd strangler-lab
npm run demo
```

The harness starts and owns a disposable loopback stack. It creates a legacy order, promotes orders to Go, creates another order, and verifies that a failing inventory batch consumes no stock. Six shadow reads cover inventory and both existing order IDs. Only completed nonempty samples can approve promotion. The observed run passed 24 contract assertions and all six comparisons.

Inventory then moves to Go with the existing stock and reservation receipts. A third order consumes four units. Healthy-service rollback restores both domains to the monolith, preserving the three order IDs and stock quantity. A fourth order is created there, followed by re-promotion. Across the run, coffee stock changes from 100 to 90; retries with the same idempotency keys return existing orders without consuming stock twice. Changed payloads reject key reuse.

The gateway holds a request barrier during state transfer. A failed transfer retains routing. Atomic inventory batches and keyed receipts handle partial validation failures and uncertain reservation responses within the running lab.

The [scorecard](https://github.com/acephos/strangler-lab/blob/main/MIGRATION_SCORECARD.md) reports the actual sample and one measured healthy-service rollback duration. Historical unsupported claims remain in the ledger with an explicit correction. None of this proves production load, crash durability, unavailable-source rollback, or safe monolith decommissioning: state is in memory, and direct service calls bypass the barrier.
