# TIL 2020.09.19
---
### Theory
- Knowledge Distillation, also known as KD, is a technique to increase the accuracy of small network
- Networks like WResNet-14, VGG-16, MobileNetV3, etc, are so small to have a good accuracy with small amount of data input
    - But with good quality of input data + data augmentation can boost up the accuracy
- So KD uses huge network, such as NasNet, EfficientNet-B7, etc. as a `teacher network` and small network as a `student network` to distill the pretrained weight of a `teacher network`
- But KD has two critical cons:
    - It normally boosts up the accuracy of the small network by 1 ~ 3%, which is not that significant
    - Also, the accuracy of small network goes <b>lower</b> after 60 epochs
        - Citation: [Link to Paper](https://arxiv.org/abs/1910.01348)
- So obviously, KD is not a panacea
- But it works well if what you need is an increase of 1 ~ 3% of accuracy
---
### Examples
- Tensorflow 2.X Example: [Knowledge_distillation_via_TF2.0](https://github.com/sseung0703/Knowledge_distillation_via_TF2.0)
- PyTorch Example: [knowledge-distillation-pytorch](https://github.com/peterliht/knowledge-distillation-pytorch)