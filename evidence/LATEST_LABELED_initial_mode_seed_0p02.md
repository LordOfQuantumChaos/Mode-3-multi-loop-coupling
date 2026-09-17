# E6 labeled n=100 — `initial_mode_seed_0p02`

## Under-claim (hard)

IC bias toward shared pump-mode shape — **NOT** coupling-discovered sync from blank IC. `all_loops` ≠ intrinsic sync lock. Keep columns independent; **NO** `fully_locked` headline.

Updated 2026-09-17 00:15:40 UTC. Label `initial_mode_seed_0p02`. HEAD `65a00ac`. ONE knob via `extra={{initial_mode_seed: 0.02}}` only. INTRINSIC_* unchanged. Production default stays `initial_mode_seed=0`. Did **not** write LATEST_CANONICAL*.

## Relation to blank-IC LATEST

This file is a **labeled** config (`initial_mode_seed=0.02` via extra). It does **not** replace `evidence/LATEST_CANONICAL_3X3_INTRINSIC.md` (production / blank-IC, `initial_mode_seed=0`). Do not quote these 100/100 rates as blank-IC intrinsic coupling sync.

## Fingerprint

- rows=3 cols=3 k=0.006 loop_lattice_velocity_only=True frames=6000 vf=0.15 bond_width=0.4 delay=0 phase_jitter=0.02 extras(pulse/PAC/GR/gyro)=off ρ=0.055 pump_mode=3
- **initial_mode_seed=0.02** (extra override only; labeled `initial_mode_seed_0p02`)
- seeds=0..99 inclusive (n=100 present)

## R/N table

| metric | R/N | rate |
|---|---|---|
| mode3_stable | 100/100 | 100.0% |
| all_loops_mode3_stable (FULL ρ) | 100/100 | 100.0% |
| pump_locked (sync_class==locked) | 100/100 | 100.0% |
| energy_sync_locked | 100/100 | 100.0% |
| energy_balance_pass | 100/100 | 100.0% |

Hard abort: none
Failed seeds (success=False): none
all_loops false seeds: none
mode3 false seeds: none

## Mean / min pairwise summary

| key | n | mean | min | max |
|---|---|---|---|---|
| mean_pairwise_corr | 100 | 0.9993 | 0.9958 | 0.9999 |
| min_pairwise_corr | 100 | 0.9965 | 0.9787 | 0.9998 |
| energy_mean_pairwise_corr | 100 | 0.9947 | 0.9645 | 0.999 |
| energy_min_pairwise_corr | 100 | 0.976 | 0.8198 | 0.9963 |

## Fail-seed status {8,17,55,57,69,89}

| seed | all_loops | mode3 | pump_locked | energy_sync | energy_balance | mean | min | energy_min | reused |
|---|---|---|---|---|---|---|---|---|---|
| 8 | True | True | True | True | True | 0.9988 | 0.9944 | 0.9786 | True |
| 17 | True | True | True | True | True | 0.9997 | 0.9983 | 0.994 | True |
| 55 | True | True | True | True | True | 0.9997 | 0.999 | 0.9932 | True |
| 57 | True | True | True | True | True | 0.9995 | 0.9982 | 0.9779 | True |
| 69 | True | True | True | True | True | 0.9998 | 0.9991 | 0.9863 | True |
| 89 | True | True | True | True | True | 0.9995 | 0.9974 | 0.9846 | True |

Mean wall s/seed: 97.8
CPU-sum wall s: 9780
Campaign wall s: 1270
Paths: `/workspace/evidence/e6/n100_labeled/`

Do not write LATEST_CANONICAL*. Do not edit INTRINSIC_*.


## Income Filter re-score (2026-09-16)

1. **KEEP** labeled `initial_mode_seed_0p02` — validated (100/100 independent columns; mins present; energy min floor ~0.82).
2. **HOLD** production / INTRINSIC default at 0 — no rewrite without Joe explicit + under-claim.
3. Blank-IC LATEST stays production baseline — labeled table stays separate.

Under-claim (hard): **IC-driven bias, not coupling-discovered sync.** HOLD E4/re-E2/E3; KILL raise-k/extras. Score closed on labeled validation.

