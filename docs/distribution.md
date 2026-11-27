# Distribution and data access

This repository contains the CrownRoute implementation, configurations and synthetic examples. Readers can run the supervision builder on their own image patches and instance-level weak boxes using the corresponding model environment. Reproducing the paper's numerical results also requires the same images, annotations, training members and weights.

## Third-party components

| Component | Use in CrownRoute | Upstream source |
| --- | --- | --- |
| Ultralytics FastSAM-s | Optional candidate generator. Users supply weights locally. The CPU example reads synthetic candidates. | [Ultralytics license](https://github.com/ultralytics/ultralytics/blob/main/LICENSE) · [FastSAM project](https://github.com/CASIA-LMC-Lab/FastSAM) |
| PyTorch and torchvision | Mask R-CNN student and its pretrained initialization. | [PyTorch license](https://github.com/pytorch/pytorch/blob/main/LICENSE) · [torchvision license](https://github.com/pytorch/vision/blob/main/LICENSE) |
| pycocotools and Pillow | COCO annotations, evaluation and image loading. | [COCO API](https://github.com/cocodataset/cocoapi) · [Pillow license](https://github.com/python-pillow/Pillow/blob/main/LICENSE) |
| OpenCV and NumPy | Image, binary-mask and array operations. | [OpenCV license](https://github.com/opencv/opencv/blob/4.x/LICENSE) · [NumPy license](https://github.com/numpy/numpy/blob/main/LICENSE.txt) |
| SciPy | Hungarian assignment for the patch-level inventory metrics in Table 6. | [SciPy license](https://github.com/scipy/scipy/blob/main/LICENSE.txt) |

Upstream providers distribute their respective implementations and model weights. Ultralytics and FastSAM list AGPL-3.0 for their source code. The original CrownRoute source code provided in this repository is licensed under the MIT License (see [LICENSE](../LICENSE)). This license does not override the licenses or attribution requirements of third-party software, pretrained models, or code carrying separate copyright notices. Such materials remain subject to their respective upstream terms.

The student loss uses torchvision's RoI mask-projection interface and retains its target-extraction structure. The repository includes the [torchvision BSD 3-Clause license notice](TORCHVISION-LICENSE.txt).

The authors keep the manuscript, original aerial images, real annotations, training masks, model weights and prediction files separately. The synthetic examples generate their inputs locally.
