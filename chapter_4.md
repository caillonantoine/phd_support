---
layout: default
title: Chapter 4
permalink: /chapter_4/
---

# Temporal Learning

Here, we present generations from our best performing model (i.e. residual transformer) using different conditioning setups.

## Unconditional generation

Several generations using the unconditional residual transformer model, either generating a sequence from scratch (generation) or continuing a ground truth audio (continuation). The plucky sound occuring at mid sample for all continuations indicates the separation between ground truth and generation.

| Mode         | Audio (coming soon)                                      |
| ------------ | -------------------------------------------------------- |
| Generation   | <audio controls /> <audio controls /> <audio controls /> |
| Continuation | <audio controls /> <audio controls /> <audio controls /> |


## Beat conditioning

Here we experiment with feeding a _clock_ to the model during both training and generation. We use a slightly modified conditioning method than the one presented in the report. Indeed, instead of feeding an array with zeros everywhere except for the beat positions, we use cyclic ramps as shown below.

![image](/phd_support/assets/clock.svg)

The ramp falling back to 0 indicates the presence of a beat. We experiment how the model reacts to changing clocks by generating an artifical clock and linearly increasing / decreasing the BPM.

| Mode           | Audio (coming soon)                                      |
| -------------- | -------------------------------------------------------- |
| Increasing BPM | <audio controls /> <audio controls /> <audio controls /> |
| Decreasing BPM | <audio controls /> <audio controls /> <audio controls /> |



## Centroid conditioning

| Mode                | Audio (coming soon)                                      |
| ------------------- | -------------------------------------------------------- |
| Increasing centroid | <audio controls /> <audio controls /> <audio controls /> |
| Decreasing centroid | <audio controls /> <audio controls /> <audio controls /> |



## Beat+centroid conditioning

| Mode                  | Audio (coming soon)                                      |
| --------------------- | -------------------------------------------------------- |
| 90bpm, low centroid   | <audio controls /> <audio controls /> <audio controls /> |
| 140bpm, high centroid | <audio controls /> <audio controls /> <audio controls /> |

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


