# TIL 20.10.09
---
### EfficientNet

- [1] Mingxing Tan and Quoc V. Le. EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks. ICML 2019. Arxiv link: https://arxiv.org/abs/1905.11946.
- EfficientNet is state-of-the-art model presented in 2019
- EfficientNet is composed of 7 MBConvs & 7 SEBlocks
- Google's EfficientNet-Lite has removed SEBlocks and changed swish activation to relu6 in order to achieve the following:
    - 1) SEBlocks do not accomplish what it is mented to do: it only increases the computational cost; by removing SEBlocks, neural network gets faster without dropping its accuracy
    - 2) Swish activation is the main cause of accuracy drop when quantizing weights; changing it to relu6 prevents the drop of accuracy when quantizing
- So, just removing SEBlocks from the network hugely improves the performance
- Aside then above, EfficientNet is widely & frequently used by many people, due to its general output: it works well with various kinds of datasets