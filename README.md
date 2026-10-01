# Animal Size Estimation

This project asks two separate questions:

- Can photos and carefully documented visual size references help estimate defined animal dimensions?
- Separately, can image-derived measurements support a useful body-weight estimate for a specified species, population, and use case when tested against actual scale weights?

These are different prediction targets. A result for one animal group, capture setup, or task does not establish performance for another.

This is an exploratory research brief, not a validated measurement tool. No project dataset, model, benchmark, or accuracy result exists. The literature notes include cattle-specific studies; those studies do not establish general performance across species.

## Visual references to investigate

- A measured calibration target deliberately placed near the animal and aligned with the relevant measurement plane
- Fixed rails, gates, panels, or platforms only when their dimensions and camera setup are verified and their relationship to the target plane is understood
- Troughs, buckets, posts, bales, vehicles, and other scene objects as context only unless their dimensions and geometry are verified

A known object calibrates its own image plane; it does not reveal the animal’s full depth or volume. A scale reference alone cannot turn a casual single view of a non-planar animal into complete 3D geometry. Test any reference cue rather than assuming it improves a result.

Define geometric size measures and body weight as separate targets. Pair dimension estimates with clearly defined physical measurements; pair any weight estimate with the same animal’s actual scale weight at a documented time. The relationship between visible dimensions and weight must be developed and validated for the specified species, population, and use case.

See [RESEARCH.md](RESEARCH.md) and [VALIDATION.md](VALIDATION.md). Do not use an unvalidated estimate for consequential animal-care decisions, medication, or sale settlement, or as a substitute for appropriate direct measurements or a scale.
