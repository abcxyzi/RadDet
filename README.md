# Wideband Radar Detection Dataset (RadDet)

This repo contains radar datasets accompanying the paper "RadDet: A Wideband Dataset for Real-Time Radar Spectrum Detection", submitted to the IEEE International Conference on Acoustics, Speech, and Signal Processing (ICASSP 2025). 

We will release a preview of our paper soon. Stay tuned for updates.

## Overview

Our experiments considered several radar datasets:

1. **RadDet-1T** - this is our proposed dataset, it contains up to 9 signal targets per frame.
2. **RadDet-9T** - this is our proposed dataset, it contains at most 1 signal target per frame.
3. **NIST-CBRS** - this is a radar dataset [created by NIST](https://www.nist.gov/publications/rf-dataset-incumbent-radar-signals-35-ghz-cbrs-band) containing at most 1 signal target per frame. We adapted the [original dataset](https://data.nist.gov/od/id/mds2-2116) and modified it in our experiments, the modified version of the dataset (NIST-CBRS) is provided here for reference. Please cite the original work by NIST if you wish to adapt their dataset in your research.

Each radar dataset contains max-hold spectrograms provided in three resolutions:

- `128 x 128` - 128 by 128 spectrograms, please refer to our paper for the specific t-f resolution.
- `256 x 256` - 256 by 256 spectrograms, please refer to our paper for the specific t-f resolution.
- `512 x 512` - 512 by 512 spectrograms, please refer to our paper for the specific t-f resolution.

## RadDet Details

RadDet introduces 11 radar classes, including 6 new LPI polyphase codes (P1, P2, P3, P4, Px, Zadoff-Chu) and a new wideband frequency-modulated continuous wave (FMCW), all coexisting across a 500 MHz band.

RadDet contains a total of 40,000 radar frames provided in three parts:
- Training set - contains 20,000 frames.
- Validation set - contains 14,000 frames.
- Test set - contains 6,000 frames.

We sample SNR from a uniform distribution to produce signal frames that fall within −20 and 20 dB at a resolution of 8 dB. This means that there are more than 6,500 unique signals genreated per SNR.

### Radar Environments

To investigate wideband spectrum detection in different scenarios, we provide RadDet in two different radar environments:

- Our sparse dataset (RadDet-1T) provides at most a single radar instance per frame whereby the probability of a radar being present in a scene is 50%.
- Our dense dataset (RadDet-9T) contains up to 9 radar instances per frame where the probability of background (noise-only) frames is 10%. RadDet-9T represents a conservative dense maritime radar environment.

## Configuration File

Each dataset contains a configuration file called `data.yaml` provided in the standard YOLO-format. An example configuration file is shown below:

```yaml
# Dataset root dir
path: ../Datasets/<DATASET_NAME>

# Train, validation, and test dataset paths (relative to path)
train: images/train
val: images/val
test: images/test

# Signal classes
names: 
  0: Rect
  1: Barker
  2: Frank
  3: P1
  4: P2
  5: P3
  6: P4
  7: Px
  8: ZadoffChu
  9: LFM
  10: FMCW
```

## Annotations

The bounding box annotations are provided as `.txt` files following the standard YOLO-format.

## Download Links

The download links for each radar dataset are provided here. We provide three resolutions:

Low resolution: `128 x 128`

- **RadDet-1T-128** - `download link will be made available soon`
- **RadDet-9T-128** - `download link will be made available soon`
- **NIST-CBRS-128** - `download link will be made available soon`

Medium resolution: `256 x 256`

- **RadDet-1T-256** - `download link will be made available soon`
- **RadDet-9T-256** - `download link will be made available soon`
- **NIST-CBRS-256** - `download link will be made available soon`

High resolution: `512 x 512`

- **RadDet-1T-512** - `download link will be made available soon`
- **RadDet-9T-512** - `download link will be made available soon`
- **NIST-CBRS-512** - `download link will be made available soon`

You can also download the original (unmodified) NIST dataset [here](https://data.nist.gov/od/id/mds2-2116).

Note, these datasets are quite large. It is recommended that you have more than 1 TB of disk storage avaialble.

## Citation

Please cite our conference paper if you find it helpful for your research. Cheers.

We will release a preview of our paper soon. Stay tuned for updates.