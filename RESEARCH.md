# Research notes

## Question

Can ordinary RGB cattle photos, visual size references found or deliberately placed in the scene, and a model trained against actual scale weights deliver a useful live-weight estimate? “Useful” is use-case dependent; no numeric acceptance limit or study result is claimed here.

## What the literature supports

- [Xiong et al. (2023), *Estimating body weight and body condition score of mature beef cows using depth images*](https://doi.org/10.1093/tas/txad085) studied 58 crossbred cows with a top-view time-of-flight depth sensor. The authors report a 22.7 kg mean absolute error on their test split for a volume-based weight regression. This is evidence about a specific depth-camera setup and cohort, not ordinary phone RGB photos or new farms.
- [Miller et al. (2019), *Using 3D Imaging and Machine Learning to Predict Liveweight and Carcass Characteristics of Live Finishing Beef Cattle*](https://doi.org/10.3389/fsufs.2019.00030) used 3D imaging with liveweights recorded by fixed weigh-crate systems and linked to animal IDs. The paper reports liveweight R² of 0.70 and RMSE of 42 kg. That controlled capture/label pipeline is materially different from arbitrary background objects in casual photos.
- [Alia et al. (2025), *Digital Innovation in Predicting Live Body Weight of Female Ongole-Grade Cattle Using Pixel Area and Morphometric Analysis*](https://doi.org/10.5398/tasj.2025.48.6.500) reports 204 female Ongole-Grade cattle, camera images, cattle-scale weights, and a known-size ruler used as an image reference. It is a relevant precedent for testing a deliberate size target; it does not establish that an ear tag or a typical farm fixture works as one.
- [OpenCV’s homography documentation](https://docs.opencv.org/4.11.0/d9/dab/tutorial_homography.html) describes the planar mapping used for a planar object. A ruler or tag can calibrate local image scale under suitable geometry; it cannot alone turn a differently positioned, non-planar cow into a metric 3D measurement.

## Implications for this question

The prior work makes image-derived body measurements worth testing, especially with depth/3D sensing or controlled capture. It does not show that a generic single photo plus a bucket, trough, fence post, or distant gate can estimate mass to an operational tolerance. Such objects may be useful scene or pose cues, but variable size, distance, perspective, and farm-specific correlations can make them misleading. A model can learn “which farm or camera” instead of body shape.

A confirmed tag SKU is a cleaner candidate than an assumed standard tag size, but its dimensions are only a local scale cue. Tag identity, tag-plane angle, pixel span, occlusion, and the distance between ear and torso all matter. Compare the tag against a body-plane calibration target and against no explicit scale cue.

## Evidence boundary

These papers are prior published studies, not results for this project. No photo inventory, tag catalog, model training, or cattle-weight benchmark has been completed here. Any public dataset would need a provenance check: confirm that each label is an individual, time-aligned liveweight from a scale rather than a target, tape estimate, seller estimate, or group average. Keep image-use rights separate from dataset access.
