---
layout: default
title: Chapter 3
permalink: /chapter_3/
---

## RAVE: A variational autoencoder for fast and high-quality neural audio synthesis

## Timbre transfer

Given the high compression applied to the input waveform when encoded into a latent representation, we demonstrate that RAVE can be used to perform timbre transfer.

### Strings to speech transfer

<img src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_timbre_2/timbre.png">

| original                                                                                                                 | reconstructed                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_timbre_2/x.mp3" controls style="width: 200px"></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_timbre_2/y.mp3" controls style="width: 200px"></audio> |

<img src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_timbre_1/timbre.png">

### Speech to strings transfer

| original                                                                                                                 | reconstructed                                                                                                            |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_timbre_1/x.mp3" controls style="width: 200px"></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_timbre_1/y.mp3" controls style="width: 200px"></audio> |

## Latent manipulation

One of the main advantages of using VAEs compared to other generative frameworks is that one can alter the reconstruction of a sample manipulating its latent representation, effectively transforming high-level attributes of the data.

Here, we show how modifying the first two dimensions of RAVE trained on darbouka impacts high-level attributes of the signal. Alteration 1 (resp. 2) has its first (resp. second) dimension set to a ramp linearly increasing from -2 to 2 over time.

| Source         | Audio                                                                                              |
| -------------- | -------------------------------------------------------------------------------------------------- |
| Original audio | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/audio/input.mp3" controls></audio>    |
| Reconstruction | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/audio/no_alter.mp3" controls></audio> |
| Alteration 1   | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/audio/dim1.mp3" controls></audio>     |
| Alteration 2   | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/audio/dim2.mp3" controls></audio>     |



## Balancing compactness and fidelity

We show the influence of the fidelity parameter _f_ on the reconstructed samples.

### Sample 1

<img src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_1/crop.png">

| original                                                                                                                          | f: 0.99                                                                                                                              | f: 0.9                                                                                                                               | f: 0.8                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_1/x.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_1/y_99.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_1/y_90.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_1/y_80.mp3" controls style="width: 100px" ></audio> |

### Sample 2

<img src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_2/crop.png">

| original                                                                                                                          | f: 0.99                                                                                                                              | f: 0.9                                                                                                                               | f: 0.8                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_2/x.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_2/y_99.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_2/y_90.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_2/y_80.mp3" controls style="width: 100px" ></audio> |

### Sample 3

<img src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_3/crop.png">

| original                                                                                                                          | f: 0.99                                                                                                                              | f: 0.9                                                                                                                               | f: 0.8                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_3/x.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_3/y_99.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_3/y_90.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_3/y_80.mp3" controls style="width: 100px" ></audio> |

### Sample 4

<img src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_4/crop.png">

| original                                                                                                                          | f: 0.99                                                                                                                              | f: 0.9                                                                                                                               | f: 0.8                                                                                                                               |
| --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ |
| <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_4/x.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_4/y_99.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_4/y_90.mp3" controls style="width: 100px" ></audio> | <audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/eval_crop/eval_crop_4/y_80.mp3" controls style="width: 100px" ></audio> |

## Bonus: sampling from the prior distribution

### Violin

<audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/random/prior_violin.mp3" controls ></audio>

### Speech

<audio src="https://github.com/acids-ircam/RAVE/raw/gh-pages/random/prior_vctk.mp3" controls ></audio>

## Bonus 2: Try RAVE yourself !

An interactive demo page is [available here](https://caillonantoine.github.io/ravejs), and allows you to try RAVE directly in your browser, without any installation needed !