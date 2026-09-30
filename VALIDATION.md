# Proposed validation

This is a study plan, not a completed experiment. First define the intended decision and acceptable error with the eventual user of the estimate; there is no universal “useful” margin to assume.

## Data and capture audit

1. Collect or identify photos with permission and actual scale-measured liveweights linked to the same animal and capture/weighing session. Record weight units, scale/source, timestamps, animal identity, farm, camera/device, view, pose, and relevant population details when available. Do not substitute lot averages, advertised target weights, tape estimates, or synthetic values for scale labels.
2. Audit candidate visual cues in a modest, permissioned sample before modeling: fixed chute/race rails, gate or panel spacing, scale platforms, feed/water troughs, buckets, fence posts, bales, vehicles, and deliberately placed rulers/boards. For each, record whether it is present, movable or installed, exact dimensions known or unknown, pixel span, angle, occlusion, and relative position/depth to the animal. For tags, record visible/legible status, confirmed SKU and component, manufacturer dimensions/source, tag angle, and pixel span. Unknown stays unknown.
3. Record body pose, camera distance/height/angle and lens if available, breed/population, and image quality. Keep consent, image-use rights, and scale-label provenance as separate checks.

## Comparisons

After a basic label and duplicate audit, compare on the same animals and views:

- A simple training-set mean/median weight baseline
- An image/body-measurement model without explicit reference-object features
- The same model plus manually confirmed tag dimensions
- The same model plus individually measured fixed-fixture or deliberate calibration-target cues
- Context-only objects as a negative-control feature set

Fit all learned transforms and regressors on training animals only. If a small regression is enough, start there; do not presume custom vision training is needed. If image features already reveal a tag, use matched tag-masked or cue-ablated views to distinguish visible-object shortcuts from added scale information.

## Split, metrics, and stopping

Keep all photos, video frames, and sessions of one animal in one split. Use a farm- or source-held-out evaluation where the data allow it; otherwise state that generalization beyond the observed farms is untested. Keep an untouched test set for one predeclared comparison. Do not tune on it.

Report animal-level MAE and RMSE in kg, bias, MAPE where weights are positive, error within the pre-agreed absolute/relative tolerance, prediction coverage and abstention reasons, interval calibration/coverage if intervals are built, worst errors, and subgroup counts. Compare paired errors for the same eligible animals and also report how many animals are excluded because the cue is missing or unreadable. A good score on the tagged subset alone is not evidence of useful whole-herd coverage.

Stop or redesign if labels are not scale-verified, cue dimensions cannot be confirmed, animals/farms leak across splits, reference cues add no useful signal, or the estimate fails the agreed tolerance or coverage. Report exploratory results honestly; do not use an unvalidated estimate for dosing, treatment, sale settlement, or other consequential decisions.
