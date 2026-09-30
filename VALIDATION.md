# Proposed validation

First define the intended task and acceptable error with its eventual user. There is no universal useful-error threshold.

## Data and cue audit

Use permissioned photos paired to the same animal’s actual scale weight at a documented capture/weighing time. Record units, scale/source, animal, farm, camera, view, pose, and relevant population details. Keep lot averages, targets, tape estimates, and synthetic labels out of the scale-weight set.

In a modest sample, inventory installed rails/gates/panels, scale platforms, troughs, buckets, posts, bales, vehicles, and deliberately placed rulers/boards. Record exact dimensions and source when known, whether fixed or movable, pixel span, angle, occlusion, and depth relative to the animal. For tags, record confirmed SKU/component, manufacturer dimensions, visibility, angle, and pixel span. Unknown stays unknown. Record camera geometry and image quality where available; treat consent, image rights, and label provenance as separate checks.

## Compare cue value

On the same animals and views, compare:
- Training-set mean/median weight
- Image/body measurements without explicit reference cues
- The same model plus manually confirmed tag dimensions
- The same model plus verified fixture or deliberate-target measurements
- Context-only objects as a negative control

Fit transforms and regressors on training animals only. Start with a small regression before assuming custom vision training is needed. If the image model can already see a tag, compare matched tag-masked images to test whether explicit tag scale adds signal.

## Split and report

Keep all views, frames, and sessions of each animal in one split. Hold out farms or sources when possible; otherwise limit generalization claims to observed conditions. Keep a final untouched test set and don’t tune on it.

Report animal-level MAE, RMSE, bias, and MAPE where valid; error within the pre-agreed tolerance; coverage, abstention reasons, and interval calibration if intervals are used; worst errors and subgroup counts. Show both paired eligible-animal errors and the fraction excluded for missing or unreadable cues.

Stop or redesign if scale labels, cue dimensions, or split independence cannot be verified, or if cues add no useful signal or the model misses the agreed error/coverage target. Do not use unvalidated estimates for dosing, treatment, or sale settlement.
