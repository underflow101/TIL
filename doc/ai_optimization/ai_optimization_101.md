# TIL 2020.09.06
---
# AI Optimization 101

## What is AI Optimization?
- To begin with, AI Optimization aims for two goals:
    - One is reducing the computational cost of the neural network(model)
    - The other one is reducing the size of the model
## Why is it needed?
- Deep neural networks have improved in a way that reduces loss and increases accuracy
    - Computational cost was often not in a consideration, until current days;
        - Sometimes small neural networks like MobileNet or SqueezeNet have introduced to the world, but the majority of deep neural networks were big, heavy, and accurate.
- Accuracy IS important, but corporations, or some field of CS needed smaller, very smaller neural networks:
    - Corporations need smaller neural networks due to the actual cost and smootheness of the service
    - Some field of CS, such as Embedded System, needed small neural networks, just to make it work
## Then why don't they build a new model that is small?
- Building a completely different neural network takes time and money
- It is also hard to prove the product reliability
- So it is better off to start with existing deep neural networks, and optimize them
## Quatization
- There are to ways to quantize the model:
    - Post-training Quantization
    - Quantization Aware Training (QAT)
- Weights of the output tensors are the key factor for accuracy, and it is stored in a form of Float32
- If you quantize that output tensors' weights to UINT8 or INT8, you have 2 benefits:
    - 1) Size of the whole model decreases by 50% ~ 75%
        - UINT8 or INT8 data type has 8 bytes of size, while Float32 has 32 bytes of size
    - 2) Computational cost reduces by 50% ~ 67%
        - Code runs faster with INT type, and runs slower with Floating Point
- But if the output tensor's weight has broader range than INT8/UINT8, it loses the feature weight while quatization, which causes reduction in accuracy
    - If this phenomenon is steep and drops accuracy a lot, you can use QAT to minimize the loss of accuracy; but it is harder to code QAT
## Pruning
- Pruning is divided into two categories:
    - Structured Pruning
    - Unstructured Pruning
- Unstructured pruning is also called weight pruning, while structured pruning is also called channel/filter/layer pruning
- Pruning removes unimportant weights to reduce the size & computational cost
- If not done carefully, pruning may affect accuracy of the model critically
