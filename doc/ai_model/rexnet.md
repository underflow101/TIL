# TIL 20.09.28
---
### ReXNet
- Citation:
<pre><code>@article{han2020rexnet,
    title={{ReXNet}: Diminishing Representational Bottleneck on Convolutional Neural Network
},
    author={Han, Dongyoon and Yun, Sangdoo and Heo, Byeongho and Yoo, YoungJoon},
    year={2020},
    journal={arXiv preprint arXiv:2007.00992},
}</code></pre>
- ReXNet (ReXNetV1) is an AI model made by NAVER ClovaAI Corp.
- When oversimplified, ReXNet is somewhat similar to the approximate shape of EfficientNet
    - At the start of the network is composed of Conv2d -> BatchNorm -> dwconv
    - Then LinearBottleneck comes out recursively (Exactly 16 times)
        - LinearBottleneck module looks similar to EfficientNet's MBConvBlock(Mobile-inverted Bottleneck Block)
            - EfficientNet's MBConvBlock comes out 7 times
        - LinearBottleneck Block includes SEBlock, which is exactly same as EfficientNet's SEBlock
    - It ends with Dropout Layer and Dense Layer
- According to the paper and actual experiment, ReXNetV1 tended to have powerful and accurate network when `width_mult` is lower
    - Until at the level of EfficientNet-B2, ReXNetV1 has better top-1 & top-5 accuracy, but with smaller size of network
    - With EfficientNet-B3 and ReXNet-2.0x, ReXNet-2.0x shows 0.1% lesser top-1 accuracy but 1.33x larger parameters
    - When EfficientNet is bigger than B3, EfficientNet tends to become more powerful than that of ReXNet

### I Wonder
- EfficientNet's SEBlock did not work properly, and removing SEBlock from EfficientNet improved inference latency in large scale, while maintaining its accuracy
- Since ReXNetV1's and EfficientNet's architecture is somewhat similar to each other, maybe removing SEBlock from ReXNet could bring the same effect that of EfficientNet's removal of SEBlock