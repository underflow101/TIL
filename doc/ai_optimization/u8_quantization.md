# TIL 2020.09.03
---

- Quantization in AI changes neural network's weights' data format
- In Tensorflow, it is divided in 3 categories:
    - Full Dynamic Range Quantization
    - Float16 Quantization
    - Full Integer Quantization
- In actual world, quantizations could be divided into following:
    - Float32 Quantization
        - Has almost no impact on AI model
    - Float16 Quantization
        - Accuracy drops (Not much)
        - Size of model decreases (> x2)
        - Computational cost stays almost the same
    - INT8 Quantization
        - Accuracy drops drastically (according to model)
        - Size of model decreases (> x4)
        - Computational cost decreases by > x2
    - UINT8 Quantization
        - Accuracy drops even more
        - Size of model decreases (> x4)
        - Computational cost decreases by > x3
        - Needs representative dataset
- UINT8/INT8 Quantization has an impact on model's accuracy only when model's output tensors' weight range is bigger than [0, 255] or [-128, 127]
    - Features that is out of range get lost

### [Tensorflow Official Doc](https://www.tensorflow.org/lite/performance/post_training_quantization)