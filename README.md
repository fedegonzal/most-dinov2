# Implementing MOST with DINO v2 (with registers)

MOST is a method for unsupervised object localization in images. The original code can be found [here](https://github.com/rssaketh/MOST)

DINO v1 is a method for self-supervised learning of visual representations. The original DINO v1 code can be found [here](https://github.com/facebookresearch/dino)

MOST uses DINO v1 as a feature extractor and later applies a fractal analysis tool to identify tokens lying on foreground patches. The identified tokens are then clustered together, and tokens of each cluster are used to generate bounding boxes on foreground regions.

This repository aims to implement MOST with the new version of DINO released on 2023, which can be found [here](https://github.com/facebookresearch/dinov2)

The paper Vision Transformers Need Registers, published on 2023, can be found [here](https://doi.org/10.48550/arXiv.2309.16588) identified some problems with feature maps of both supervised and self-supervised ViT (Vision Transformer) models. This "artifacts" correspond to high-norm tokens appearing during inference primarily in low-informative background areas of images, that are repurposed for internal computations.

DINO v2 has published a new version of the code that solves this problem by adding a register to the model. Both, the original and the new version, can be found at the DINO v2 repository.
