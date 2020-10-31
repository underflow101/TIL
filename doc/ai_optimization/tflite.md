# TIL 2020.10.31
---

### Tensorflow Lite
- Tensorflow Lite is an AI optimization framework made by Google.
- Tensorflow Lite is, however, not a stand-alone package; it is inside the Tensorflow package.
- To use Tensorflow Lite, you just need to import `tensorflow.lite`.
- Tensorflow Lite package mainly offers `interpreter` & `converter`.
    - `interpreter` can import tflite converted AI models and infer the results.
    - `converter` converts Tensorflow SavedModel pb file or Keras h5 file into tflite file.
- Tensorflow Lite also offers quantization(Float32, Float16, INT8, UINT8, UINT8 with INT16 Activation Functions), which increases inference speed and reduces model size.
- Tensorflow Lite compresses AI models so that it can be fit inside Mobile environments or Embedded System.