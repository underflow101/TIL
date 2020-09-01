# TIL 2020.09.01
---

- Network Slimming is one of the model pruning techniques
    - Under category of structured pruning, Network Slimming is one of the automatic structured pruning
    - Target: channels with lower **scaling factors**
    - Imposes L1-sparsity on **channel-wise scaling factors** from Batch Normalization layers during training
    - Produces automatically discovered target architectures
- Citation: [Paper URL](https://arxiv.org/abs/1708.06519v1)
<pre><code>
    Zhuang Liu, Jianguo Li, Zhiqiang Shen, Gao Huang, Shoumeng Yan, Changshui Zhang,
    Learning Efficient Convolutional Networks Through Network Slimming,
    arXiv:1708.06519, 2017
</code></pre>

- Tensorflow Keras (TF 2.x) Example: [Tensorflow Example](https://github.com/TianzhongSong/Network-Slimming-Keras/blob/master/utils/channel_pruning.py)
- PyTorch Example: [PyTorch Example](https://github.com/foolwood/pytorch-slimming)
- Caffe Example: [Caffe Example](https://github.com/eezywu/Caffe-Network-Slimming)