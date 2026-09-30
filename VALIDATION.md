# Proposed validation

There is no universal useful-error threshold. Define the intended species, population, measurement target, use case, and acceptable error with its eventual user before testing. Keep geometric size and body weight as separate outcomes: each needs its own ground truth, model evaluation, and species-appropriate validation. Results from one animal group or capture setting do not establish performance for another.

## Define the target

- For geometric size, specify the physical dimension or dimensions, anatomical landmarks, units, pose, and measurement method. Decide whether the target is a 2D image measure, a metric body dimension, or a 3D measure such as volume.
- For body weight, use actual scale weight from the same animal at a documented capture/weighing time. Any relationship between visible dimensions and weight must be trained and tested for the specified species, population, and use case; do not assume a universal conversion.
- Set the acceptable error and any required coverage or abstention behavior before inspecting test results.

## Data and cue audit

Use permissioned photos paired with the appropriate physical measurement from the same animal and a documented time. For weight labels, record units, scale/source, capture-to-weighing interval, animal, population, farm, camera, view, pose, and relevant population details. For size labels, document how each physical dimension was measured and by whom. Keep lot averages, targets, tape estimates, and seller estimates out of the scale-weight set.

Inventory installed rails/gates/panels, platforms, troughs, buckets, posts, bales, vehicles, and deliberately placed rulers or boards. Record exact dimensions and their source when known, whether fixed or movable, pixel span, angle, occlusion, and depth relative to the animal. For tags, record confirmed SKU/component, manufacturer dimensions, visibility, angle, and pixel span. Unknown stays unknown. Record camera geometry and image quality where available; treat consent, image rights, and label provenance as separate checks.

## Compare cue value

For the selected species and target, compare on the same animals and views:
- Training-set mean/median baseline for the target
- Image/body measurements without explicit reference cues
- The same approach plus verified reference dimensions
- Context-only objects as a negative control

Keep size and weight as separate outcomes and report both only if each was evaluated. Fit transformations and regressors on training animals only. Start with a small regression before assuming custom vision training is needed. If the image model can already see a tag, compare matched tag-masked images to test whether explicit tag scale adds signal.

## Split and report

Keep all views, frames, and sessions of each animal in one split. Hold out farms or sources when possible; otherwise limit generalization claims to observed conditions. Keep a final untouched test set and don’t tune on it.

For weight, report animal-level MAE, RMSE, bias, and MAPE where valid. For dimensions, report error by measured dimension, with units and an appropriate relative error where useful. For each target, report error within the pre-agreed tolerance, coverage, abstention reasons, and interval calibration if intervals are used; show worst errors and subgroup counts. Show both paired eligible-animal errors and the fraction excluded for missing or unreadable cues.

Stop or redesign if measurement labels, cue dimensions, or split independence cannot be verified, or if cues add no useful signal or the method misses the agreed error/coverage target. Do not use unvalidated estimates for dosing, treatment, or sale settlement. The cattle studies cited in [RESEARCH.md](RESEARCH.md) are literature precedents only; they do not validate this proposed protocol or a general method across animals.
