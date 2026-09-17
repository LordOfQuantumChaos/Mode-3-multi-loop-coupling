# Judge pitch (one page) — orchestration + Mode-3

**What you’re judging:** a working multi-agent setup that keeps scientific claims honest while shipping a public, runnable physics package.

**Public artifact:** this repository ([Mode-3 Multi-Loop Coupling](https://github.com/LordOfQuantumChaos/Mode-3-multi-loop-coupling))  
**Orchestration story:** a Chief of Staff bot routes work to specialist bots (lattice, evidence, claim guard, income filter) — claim boundaries before merge, labeled configs kept separate from production.

Outsider runbook: [`JUDGE_DEMO.md`](JUDGE_DEMO.md). Claim limits: [`CLAIM_BOUNDARY.md`](../CLAIM_BOUNDARY.md).

---

## 60–90 second demo

```bash
git clone https://github.com/LordOfQuantumChaos/Mode-3-multi-loop-coupling.git
cd Mode-3-multi-loop-coupling
python -m venv .venv && source .venv/bin/activate
pip install -e ".[dev]"
python -m mode3_coupling demo    # ends === Demo OK === ; prints fingerprint
python -m mode3_coupling smoke   # short run; not production rates
python -m mode3_coupling test    # unit tests
```

**Fingerprint (quote with any rates):** 3×3, k=0.006, velocity_only=True, vf=0.15, bond=0.4, jitter=0.02, **initial_mode_seed=0**, ρ=0.055, extras off.

---

## Evidence (do not mix columns)

| Column | Config | mode3 | all_loops (FULL ρ) | pump_locked | energy_sync |
|--------|--------|------:|-------------------:|------------:|------------:|
| **Blank-IC production** | seed=0 (canonical LATEST) | 100/100 | **94/100** | 19/100 | 4/100 |
| **Labeled IC-seeded** | seed=0.02 via *extra* only | 100/100 | 100/100 | 100/100 | 100/100 |

- Blank-IC misses for all_loops: {8, 17, 55, 57, 69, 89}.
- **Under-claim (hard):** labeled 100/100 is IC-shared pump-mode *bias*, not blank-IC coupling discovery. Production default stays seed=0.
- Metrics are independent — no “fully locked” headline from mixing columns.
- Patent: **pending** provisional App. 64/119,833 — not “patented.”

Sources: `evidence/LATEST_CANONICAL_3X3_INTRINSIC.md`, `evidence/LATEST_LABELED_initial_mode_seed_0p02.md`, `CLAIM_BOUNDARY.md`.

---

## Why this is useful

1. **Runnable in under two minutes** — clone, demo, smoke, tests.
2. **Honesty as product** — full all_loops gate (dominant mode *and* per-loop stable); fingerprint always with rates; claim review before merge.
3. **Orchestration that leaves an audit trail** — scouts, labeled vs intrinsic, promote/park/kill decisions, under-claims kept in-repo.

---

## What we are not claiming

- Hardware or issued-patent status.
- Blank-IC sync lock from labeled E6 rates.
- That short demo/smoke frames equal n=100 production rates.
- That residual 6/100 all_loops misses are “solved” (blank-IC knob scouts E5/E7 did not promote).
