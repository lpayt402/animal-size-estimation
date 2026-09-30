# Research notes

## Question

Can ordinary RGB cattle photos, visual references in the scene, and a model trained on actual scale weights yield a useful live-weight estimate?

## Relevant prior evidence

- [Xiong et al. (2023)](https://doi.org/10.1093/tas/txad085) used top-view time-of-flight depth images from 58 crossbred cows. Their volume-based regression reported 22.7 kg mean absolute error on its test split. This is a specific depth-camera study, not ordinary phone photos or a new-farm validation.
- [Miller et al. (2019)](https://doi.org/10.3389/fsufs.2019.00030) paired 3D images with weights and animal IDs from fixed weigh-crate systems. The paper reports liveweight R² 0.70 and RMSE 42 kg. That capture and label pipeline differs from casual photos with incidental objects.
- [Alia et al. (2025)](https://doi.org/10.5398/tasj.2025.48.6.500) studied 204 female Ongole-Grade cattle using camera images, cattle-scale weights, and a 48 × 100 mm ruler as an image reference. It is a precedent for testing a deliberate target, not evidence that a tag or typical farm fixture works.
- [OpenCV’s homography guide](https://docs.opencv.org/4.11.0/d9/dab/tutorial_homography.html) describes mapping between planes. A known object can help calibrate its own plane; it does not alone make a differently positioned, non-planar cow a metric 3D measurement.

## What this does and doesn’t imply

Published work supports testing image-derived body measurements, especially with depth/3D sensing or controlled capture. It does not establish that a single casual photo plus a bucket, trough, fence post, or distant gate meets any useful error tolerance. Those objects may add scene context, but variable size, perspective, distance, and farm-specific correlations can mislead a model.

A confirmed tag SKU is a cleaner size reference than an assumed standard, but tag-plane angle, occlusion, pixel span, and distance from the torso matter. Compare it with a deliberate body-plane target and with no explicit size cue.

No photo inventory, tag catalog, model training, or cattle-weight benchmark has been completed for this project. Any dataset needs label and rights checks: confirm individual, time-aligned liveweights from a scale, not targets, tape estimates, seller estimates, or group averages. Image-use rights are separate from data access.
