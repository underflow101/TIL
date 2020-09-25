# TIL 2020.09.25
---
### Model Compression
- Model compression is basically the most important part of AI Optimization & On-Device AI
- Changing from Python language to C++ language, while using Tensorflow Lite Framework, only brings minuscule impact on inference latency
    - For Raspberry Pi 3B+, EfficientNet-B0 (UINT8 Quantized):
        - While using Python language, it takes 442 [ms] for `interpreter.invoke()`
        - While using C++ language, it takes 440 [ms] for `interpreter->Invoke();`
    - So it shows basically NO difference using Python or C++
        - Python is just a wrapper, not the inferencing code
- So it is better off to decrease the size of input tensor (input image)
    - For example, diminishing the input size of tensor from (224, 224, 3) to (100, 100, 3) gives 4x speed of inference
- Changing activation function from swish() -> relu6() also improves inference latency
    - EfficientNet-Lite has increased its performance with this method
- Pruning (Structured/Unstructured), Quantization, and so on are also part of the model compressing methods
- Delete unnecessary layers, or blocks like SEBlocks to improve the inference latency