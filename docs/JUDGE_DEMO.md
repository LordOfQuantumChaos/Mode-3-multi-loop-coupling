# Judge demo (60–90 seconds)

**Repo:** Mode-3 Multi-Loop Coupling (public evaluation package)  
**Purpose:** What an outsider / challenge judge should run.  
**Not:** Production multi-seed rates, hardware claims, or an issued patent.

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
| 2 | `python -m mode3_coupling smoke` | Short 3×3 integrate; prints fingerprint + `mode3_stable` / `all_loops_mode3_stable` / sync mean (and min when present). |
| 3 | `python -m mode3_coupling test` | Unit tests pass. |

## How to read the output

- **Fingerprint** (3×3, k=0.006, velocity_only, bond_width, frames, ρ, extras off) must be quoted with any rates.
- **Short demo/smoke runs are not production-length rates.** Do not treat them as the multi-seed campaign.
- **`all_loops_mode3_stable`** requires dominant pump mode **and** per-loop ρ / `stable` — not dominant-only.
- **`pump_locked` / sync class** is mean pairwise pump-amplitude correlation ≥ 0.85. Always also look at **min** pairwise. Class lock ≠ tight lattice lock.
- Patent status: **pending** provisional App. **64/119,833** — not “patented.”

## Claim boundary

See [`CLAIM_BOUNDARY.md`](../CLAIM_BOUNDARY.md). Prefer under-claiming.

## Multi-seed evidence

When present, see `evidence/LATEST_CANONICAL_3X3_INTRINSIC.md`. Do not cite older `all_loops` rates measured under a dominant-only bit after the honesty gate change.
