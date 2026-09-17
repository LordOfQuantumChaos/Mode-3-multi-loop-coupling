# Evidence summary

**Status:** Configuration-specific **simulation** observations.  
**Not:** hardware warranty or universal mode-3 guarantee.

## Where files live

| File | Role |
|------|------|
| `evidence/LATEST_CANONICAL_3X3_INTRINSIC.md` | Blank-IC production multi-seed summary (`initial_mode_seed=0`) |
| `evidence/LATEST_CANONICAL_3X3_INTRINSIC.json` | Blank-IC rates + config |
| `evidence/LATEST_LABELED_initial_mode_seed_0p02.md` | Labeled IC-seeded campaign (`initial_mode_seed=0.02`) |
| `evidence/LATEST_LABELED_initial_mode_seed_0p02.json` | Labeled rates + config |
| `evidence/PHASE_ENERGY_DECOUPLING.md` | Phase vs energy metric separation |
| `PHASE_ENERGY_DECOUPLING.md` (root) | Package narrative |

## How to read results

Always note:

1. **Config** — rows, cols, k, frames, velocity-only, velocity_frac, bond_width, phase_jitter, **initial_mode_seed**, pulse flags, ρ gate  
2. **Seed set** — which seeds, how many  
3. **Metric column** — mode-3 rate ≠ phase-lock rate ≠ energy-lock rate  
4. **Blank-IC vs labeled** — never substitute labeled 100/100 for blank-IC LATEST

## Pinned rates (confirm against LATEST files)

### Blank-IC canonical (`initial_mode_seed=0`)

| Metric | Rate |
|--------|------|
| mode3_stable | 100 / 100 |
| all_loops_mode3 (FULL ρ) | 94 / 100 |
| pump_locked (class / mean) | 19 / 100 |
| energy_sync_locked | 4 / 100 |
| energy_balance | 100 / 100 |

### Labeled `initial_mode_seed_0p02` (extra only; prod default still 0)

| Metric | Rate |
|--------|------|
| mode3 / all_loops / pump / energy_sync / balance | 100 / 100 |

**Under-claim:** IC bias toward shared pump-mode shape — not blank-IC coupling-discovered sync.

## Typical campaign shape

- Lattice: 3×3 intrinsic  
- Frames: 6000 (production-style)  
- Seeds: 0…99  
- Coupling: k = 0.006, velocity_only=True, vf=0.15, bond=0.4, jitter=0.02  
- Gate: ρ = 0.055  
- Extras: off  

## Reproducing evidence (advanced)

Full regeneration can take a long time (especially 100×6000f).  
This public GitHub package prioritizes:

1. Unit tests (seconds)  
2. Demo / smoke (seconds–minutes)  
3. Published LATEST evidence files (read-only snapshot)

Long campaign scripts may live in the inventor monorepo; not required for drop-in use.

## Scientific reporting template

> Under config C (3×3, k=…, frames=…, ρ=…, initial_mode_seed=…), for seeds S₁…Sₙ,  
> mode-3 lattice success was **R/N**.  
> Phase and energy classes are reported separately (see table).  
> Results are simulation-only. Labeled IC-seeded rates are not blank-IC production rates.
