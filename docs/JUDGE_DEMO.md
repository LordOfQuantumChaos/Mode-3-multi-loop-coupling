# Judge demo (60–90 seconds)

**Repo:** Mode-3 Multi-Loop Coupling (public evaluation package)  
**Purpose:** What an outsider / challenge judge should run.  
**Not:** Production multi-seed rates, hardware claims, or an issued patent.

One-page pitch (orchestration + evidence tables): [`JUDGE_PITCH.md`](JUDGE_PITCH.md).

## Setup

```bash
git clone https://github.com/LordOfQuantumChaos/Mode-3-multi-loop-coupling.git
cd Mode-3-multi-loop-coupling
python -m venv .venv
# Windows: .\.venv\Scripts\Activate.ps1
source .venv/bin/activate
pip install -e ".[dev]"
```

## Commands

| Step | Command | Expect |
|------|---------|--------|
| 1 | `python -m mode3_coupling demo` | Ends with `=== Demo OK ===`. Prints production **fingerprint** and short-run metrics. |
| 2 | `python -m mode3_coupling smoke` | Short 3×3 integrate; prints fingerprint + `mode3_stable` / `all_loops_mode3_stable` / sync mean **and min** pairwise when the run succeeds. |
| 3 | `python -m mode3_coupling test` | Unit tests pass. |

## How to read the output

- **Fingerprint** must be quoted with any rates: 3×3, k=0.006, velocity_only=True, velocity_frac=0.15, bond_width=0.4, phase_jitter=0.02, **initial_mode_seed=0**, frames, ρ=0.055, pump_mode=3, extras off.
- **Short demo/smoke runs are not production-length rates.** Do not treat them as the multi-seed campaign.
- Short smoke may show `mode3_stable=False` — **expected at short frames**, not a failed package.
- **`all_loops_mode3_stable`** requires dominant pump mode **and** per-loop ρ / `stable` — not dominant-only.
- **`pump_locked` / sync class** is mean pairwise pump-amplitude correlation ≥ 0.85. Always also look at **min** pairwise. Class lock ≠ tight lattice lock.
- Patent status: **pending** provisional App. **64/119,833** — not “patented.”

## Claim boundary

See [`CLAIM_BOUNDARY.md`](../CLAIM_BOUNDARY.md). Prefer under-claiming.

## Multi-seed evidence (do not mix columns)

### Blank-IC production (canonical)

`evidence/LATEST_CANONICAL_3X3_INTRINSIC.md` — `initial_mode_seed=0`, velocity_only, FULL ρ gate:

| Metric | Rate |
|--------|------|
| mode3_stable | 100 / 100 |
| all_loops_mode3 (FULL ρ) | **94 / 100** |
| pump_locked (class / mean) | 19 / 100 |
| energy_sync_locked | 4 / 100 |

Miss seeds for all_loops: {8, 17, 55, 57, 69, 89}. Do not cite older dominant-only 95/100.

### Labeled IC-seeded (optional, separate)

`evidence/LATEST_LABELED_initial_mode_seed_0p02.md` — `initial_mode_seed=0.02` via extra only:

| Metric | Rate |
|--------|------|
| mode3 / all_loops / pump / energy_sync | 100 / 100 each |

**Under-claim (hard):** IC-shared pump-mode shape bias — **not** blank-IC coupling discovery. Do **not** quote these 100/100 as production blank-IC rates. Production demo/fingerprint remains `initial_mode_seed=0`.
