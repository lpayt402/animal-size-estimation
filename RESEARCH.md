# Research notes: animal size estimation

## Research questions

- For a specified species and use case, can ordinary images plus documented visual references support estimates of defined physical dimensions?
- Separately, can image-derived dimensions support body-weight estimates for a specified species, population, and use case when trained and tested against actual scale weights?

Geometric size and body weight are different targets. A relationship between dimensions and weight is species- and population-specific; a result for one animal group, sensor, capture setup, or task does not establish performance for another.

## Evidence boundaries

The literature below contains cattle-specific examples. It supports investigating particular methods in their studied settings, not a general animal-size result, casual-phone-photo accuracy, or transfer to another species or farm.

- [Xiong et al. (2023)](https://doi.org/10.1093/tas/txad085) used top-view time-of-flight depth images from 58 crossbred cows. Their volume-based regression reported 22.7 kg mean absolute error on its test split. This is a specific depth-camera study, not ordinary phone photos or a new-farm validation.
- [Miller et al. (2019)](https://doi.org/10.3389/fsufs.2019.00030) paired 3D images with weights and animal IDs from fixed weigh-crate systems. The paper reports liveweight R² 0.70 and RMSE 42 kg. That capture and label pipeline differs from casual photos with incidental objects.
- [Alia et al. (2025)](https://doi.org/10.5398/tasj.2025.48.6.500) studied 204 female Ongole-Grade cattle using camera images, cattle-scale weights, and a 48 × 100 mm ruler as an image reference. It is a precedent for testing a deliberate target in that setting, not evidence that tags, typical farm fixtures, or methods for other animals work.
- [OpenCV’s homography guide](https://docs.opencv.org/4.11.0/d9/dab/tutorial_homography.html) describes mapping between planes. A known object can help calibrate its own plane; it does not alone make a differently positioned, non-planar animal a metric 3D measurement.

## What this does and doesn’t imply

Published work supports testing image-derived measurements, especially with depth/3D sensing or controlled capture. The cited cattle findings do not establish that a single casual photo plus a bucket, trough, fence post, or distant gate meets any useful error tolerance. Such objects may add scene context, but variable size, perspective, distance, and farm-specific correlations can mislead a model.

A confirmed tag SKU is a cleaner size reference than an assumed standard, but tag-plane angle, occlusion, pixel span, and distance from the torso matter. Compare it with a deliberate target and with no explicit size cue rather than assuming it helps.

For any weight task, labels and evaluation must match the specified species, population, capture conditions, and intended use. Confirm individual, time-aligned liveweights from a scale, not targets, tape estimates, seller estimates, or group averages. Image-use rights are separate from data access.

No photo inventory, dataset, model training, or benchmark has been completed for this project. Any future result must be reported for the species, population, measurement target, and conditions actually evaluated.
