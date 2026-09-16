# Canonical 3x3 intrinsic lattice evidence

**This run only.** Honest n=100. Frames=6000 (never shortened). HEAD `65a00ac`. Patent 64/119,833.

Do **not** headline `fully_locked`. Independent metrics below; do not quote older 19/100 copy as measured.

## Fingerprint

| key | value |
|---|---|
| git_note | public zip main 65a00ac; all_loops_mode3_stable is FULL rho gate |
| git_sha | `65a00ac` |
| lattice | rows=3, cols=3, k=0.006 |
| loop_lattice_velocity_only | True |
| frames | 6000 |
| pump_mode | 3 |
| rho (pump_stability_rel_var) | 0.055 |
| pulse | off (`traveling_pulse_enabled=False`) |
| PAC | off (`predictive_adaptive_controller_enabled=False`) |
| GR | off (`gr_well_enabled=False`, `gr_strength=0.0`) |
| gyro | off (`gyro_enabled=False`) |
| gyro_pll | off (`gyro_pll_memory_enabled=False`) |
| seeds | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99 |
| n_seeds | 100 |
| base | `INTRINSIC_LATTICE_3X3_DEFAULT` via `driven_loop.stress.run_seed` |
| extras in merged config | {"adaptive_gyro_memory_enabled": false, "enable_central_potential": false, "frames": 6000, "gr_gyro_barrier_enabled": false, "gr_orbital_steering_enabled": false, "gr_strength": 0.0, "gr_well_enabled": false, "gyro_enabled": false, "gyro_pll_memory_enabled": false, "loop_lattice_cols": 3, "loop_lattice_coupling": 0.006, "loop_lattice_enabled": true, "loop_lattice_rows": 3, "loop_lattice_spacing": 2.4, "loop_lattice_velocity_only": true, "plasma_enabled": false, "predictive_adaptive_controller_enabled": false, "pump_mode": 3, "pump_stability_rel_var": 0.055, "radiation_impact_enabled": false, "traveling_pulse_enabled": false, "traveling_pulse_inter_loop_transfer": false} |

## Independent metrics (R/N from this run)

| metric | R/N | rate |
|---|---|---|
| mode3_stable (`stress.mode3_stable`) | 100/100 | 100.0% |
| all_loops_mode3_stable (**FULL ρ gate on 65a00ac: dominant_mode==3 AND per-loop stable**) | 94/100 | 94.0% |
| pump_locked (`sync_class==locked`) | 19/100 | 19.0% |
| energy_sync_locked (`energy_sync_class==locked`) | 4/100 | 4.0% |
| energy_balance_pass (`abs(energy_balance)<=0.01`) | 100/100 | 100.0% |

## Failed seeds (`success=False` or exception)

(none)

## Lock vs mode-3 (short)

Pump lock (`pump_locked`) is pairwise pump-amplitude correlation >= 0.85 over the tail. It is **independent** of `mode3_stable` (stable oscillation + dominant mode 3 + pump-variance <= 0.055 on the primary loop). Energy lock is the same correlation test on stored-energy traces. Public `all_loops_mode3_stable` on 65a00ac is the **FULL ρ gate** (every loop `dominant_mode==pump_mode` AND per-loop `stable` / pv < ρ). Do not quote the old 95/100 dominant-only rate.

Mean wall seconds / seed: 94.26397000000001.
CPU-sum wall seconds: 9426.397.
Updated: 2026-09-16 20:40:06 UTC.

## Sync mean vs min

This campaign API did **not** populate `min_pairwise_corr` in the aggregate table. Do not treat `pump_locked` (mean≥0.85) as tight lattice lock without per-seed min pairwise. Prefer quoting mode3 / all_loops (FULL ρ) with fingerprint; report pump_locked as class lock only.
