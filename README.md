# Can an ordinary cattle photo help estimate live weight?

I’m exploring a practical research question: can ordinary cattle photos, a few verified visual size references, and models trained on actual scale weights produce estimates within a useful error range? The useful range depends on the intended job and has not been set yet.

This is a question-first research project, not a livestock scale or a validated model. There are no cattle photos, trained weights, benchmark results, or accuracy claims here.

## Reference cues worth testing

A first photo audit could record:

- Fixed chute or race rails, gate frames, panel spacing, or a scale platform, only when the exact fixture dimensions and camera setup are known
- A calibration ruler/board intentionally placed near the animal’s body, or an ear tag whose exact SKU and physical dimensions are confirmed
- Feed or water troughs, buckets, hay bales, fence posts, and vehicles as scene context only; their dimensions, positions, and distance from the cow can vary

A reference object can help convert pixels to length near its own plane. It does not by itself recover the cow’s depth or volume. An ear tag is small, can be tilted or hidden, and sits on a different plane from much of the torso. Its value needs a paired test, not an assumption.

## What would answer the question

Use photos paired to the same animal’s actual scale weight, then compare an image/body-measurement baseline with verified tag and fixture cues. Keep every view of an animal together during evaluation, and test on held-out farms or capture setups where possible. Define “useful error” for a real use case before looking at results.

See [RESEARCH.md](RESEARCH.md) for the evidence boundary and [VALIDATION.md](VALIDATION.md) for a proposed test. No estimate should be used for dosing, sale settlement, or as a substitute for a scale.
