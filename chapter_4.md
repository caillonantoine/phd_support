---
layout: default
title: Chapter 4
permalink: /chapter_4/
---

# Temporal Learning

Here, we present generations from our best performing model (i.e. residual transformer) using different conditioning setups.

## Unconditional generation

Several generations using the unconditional residual transformer model continuing a ground truth audio. The plucky sound occuring at mid sample for all continuations indicates the separation between ground truth and generation.

| Metrics                                                      | Audio                                                                                          |
| ------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| ![metrics](/phd_support/assets/chapter4/unconditional_0.svg) | <audio src="/phd_support/assets/chapter4/unconditional_0.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/unconditional_1.svg) | <audio src="/phd_support/assets/chapter4/unconditional_1.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/unconditional_2.svg) | <audio src="/phd_support/assets/chapter4/unconditional_2.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/unconditional_3.svg) | <audio src="/phd_support/assets/chapter4/unconditional_3.mp3" style="width: 100px;" controls/> |

## Beat conditioning

Here we experiment with feeding a _clock_ to the model during both training and generation. We use a slightly modified conditioning method than the one presented in the report. Indeed, instead of feeding an array with zeros everywhere except for the beat positions, we use cyclic ramps as shown below.

![image](/phd_support/assets/clock.svg)

The ramp falling back to 0 indicates the presence of a beat. We experiment how the model reacts to changing clocks by generating an artifical clock and linearly increasing / decreasing the BPM.

### Unmodified beat track

We present several continuations conditioned on the original beat track. We additionally include a tempo indicator corresponding to the beat conditioning signal in the right audio channel.

| Metrics                                             | Audio                                                                                 |
| --------------------------------------------------- | ------------------------------------------------------------------------------------- |
| ![metrics](/phd_support/assets/chapter4/sync_0.svg) | <audio src="/phd_support/assets/chapter4/sync_0.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/sync_1.svg) | <audio src="/phd_support/assets/chapter4/sync_1.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/sync_2.svg) | <audio src="/phd_support/assets/chapter4/sync_2.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/sync_3.svg) | <audio src="/phd_support/assets/chapter4/sync_3.mp3" style="width: 100px;" controls/> |

### Linearly increasing BPM

Here, we experiment with modifying the beat track _during_ generation. More specifically, we use the original beat track during the first half of the generation, and linearly increase it to 120% of its original speed over the second half. Overall, the model is struggling to follow the modified beat track, which might be an indication that the conditioning signal is not strong enough, or the method used to extract the beat track is not precise enough to provide a reliable source of information.

| Metrics                                                 | Audio                                                                                     |
| ------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| ![metrics](/phd_support/assets/chapter4/sync_mod_0.svg) | <audio src="/phd_support/assets/chapter4/sync_mod_0.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/sync_mod_1.svg) | <audio src="/phd_support/assets/chapter4/sync_mod_1.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/sync_mod_2.svg) | <audio src="/phd_support/assets/chapter4/sync_mod_2.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/sync_mod_3.svg) | <audio src="/phd_support/assets/chapter4/sync_mod_3.mp3" style="width: 100px;" controls/> |

## Beat+Centroid conditioning

Finally, we experiment with conditioning the model on both a beat track and a centroid extracted from the original audio. We evaluate the effect of the centroid conditioning by biasing the target centroid using an linearly increasing (resp. decreasing) ramp used to bias the original centroid.

### Increasing bias

| Metrics                                                                 | Audio                                                                                                     |
| ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_0_increasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_0_increasing.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_1_increasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_1_increasing.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_2_increasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_2_increasing.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_3_increasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_3_increasing.mp3" style="width: 100px;" controls/> |

### Decreasing bias

| Metrics                                                                 | Audio                                                                                                     |
| ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_0_decreasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_0_decreasing.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_1_decreasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_1_decreasing.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_2_decreasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_2_decreasing.mp3" style="width: 100px;" controls/> |
| ![metrics](/phd_support/assets/chapter4/centroid_sync_3_decreasing.svg) | <audio src="/phd_support/assets/chapter4/centroid_sync_3_decreasing.mp3" style="width: 100px;" controls/> |

<hr>
<br>

# Early results

The following generations / pieces have been generated using an early version of the unconditional shifted convolutional model, and a RAVE model with post training discretization.

|           Dataset           | Generation                                                                                                     |
| :-------------------------: | -------------------------------------------------------------------------------------------------------------- |
|   **Darbouka** _(stereo)_   | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/audio/docs_darbouka_prior.mp3" controls></audio>  |
|      **VCTK** _(mono)_      | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/audio/hierarchical.mp3" controls></audio>         |
|     **Violin** _(mono)_     | [![ACIDS](http://img.youtube.com/vi/XXqQyeXZpl0/mqdefault.jpg)](https://www.youtube.com/watch?v=XXqQyeXZpl0)   |
| **Archive (v1)** _(stereo)_ | [![archive](http://img.youtube.com/vi/L2eVjMMvb2A/mqdefault.jpg)](https://www.youtube.com/watch?v=L2eVjMMvb2A) |
