---
description: Parameter-efficient fine-tuning
---

# PEFT

Fine-tuning large language models (LLMs) is challenging due to the immense computational resources required. There are several prominent parameter-efficient fine-tuning (PEFT) approaches to enable this more efficiently, including:

### Prompt Tuning

This involves only updating a small set of continuous prompt embeddings prepended to the input, while keeping the LLM's parameters frozen. It is highly efficient but can underperform compared to full fine-tuning.

### Adapter Methods

These insert small adapter modules like bottleneck layers or attention layers into the LLM's architecture. Only the parameters of these lightweight adapters are updated during fine-tuning.

### Reparameterization Methods

These aim to reparameterize the LLM's weight updates into a lower-dimensional subspace:

### Low-Rank Adaptation (LoRA)

LoRA reparameterizes the weight updates as low-rank matrices, significantly reducing the number of trainable parameters. It has been shown to match or even outperform full fine-tuning on many tasks while being highly efficient.

<details>

<summary>LoRA</summary>

Low-rank adaptation (LoRA) has emerged as a transformative approach that addresses these challenges by significantly reducing the computational burden and memory requirements associated with fine-tuning.

LoRA, which stands for Low-Rank Adaptation, introduces an innovative method for adapting pre-trained models to new tasks.

Instead of updating a large model's parameters, which can number billions, LoRA focuses on modifying smaller parameters by decomposing the weight updates into low-rank matrices.

The fundamental tenet of LoRA is that low-rank approximations can efficiently capture the adaptations needed for new tasks.

In traditional fine-tuning, every parameter in the model is updated, leading to high computational and memory costs. LoRA introduces a pair of low-rank matrices into each neural network layer.

Only these low-rank matrices are optimized during training, while the original pre-trained weights remain fixed.

This results in a substantial reduction in the number of trainable parameters and, consequently, a significant decrease in training time and memory usage.

One of LoRA's key advantages is its cost-effectiveness. By reducing the number of parameters that need to be updated, LoRA minimizes the computational resources required for fine-tuning, making it feasible to adapt large models even on standard hardware.

This lowers the entry barrier for organizations with limited computational resources and reduces energy consumption, contributing to more sustainable AI practices.

Despite reducing the number of trainable parameters, models fine-tuned with LoRA maintain high performance. The low-rank matrices can capture the essential task-specific information needed to adapt the pre-trained model to new domains.

Empirical studies have shown that LoRA can achieve performance comparable to, and sometimes surpassing, traditional fine-tuning methods.

Rapidly adapting to new threats and regulatory changes is crucial in fraud detection and anti-money laundering (AML). LoRA can help by allowing models to be fine-tuned quickly without the high costs usually associated with this process.

[Link](https://www.linkedin.com/posts/danny-butvinik\_artificialintelligence-machinelearning-datascience-activity-7201062125853634560-z0T-/?utm\_source=share\&utm\_medium=member\_ios)

</details>

### Quantization-Aware LoRA (QLoRA)

QLoRA combines LoRA with quantization to further reduce memory requirements during fine-tuning by using 4-bit quantized weights for the frozen LLM. The key advantages of PEFT methods like LoRA and QLoRA are:

1. Reduced memory and compute requirements for fine-tuning
2. Avoiding catastrophic forgetting of the LLM's pre-trained knowledge
3. Enabling easier multi-task adaptation by simply switching the lightweight tuned components

Among these, LoRA and its variants like QLoRA have emerged as leading PEFT approaches, offering an excellent trade-off between efficiency and performance on a wide range of tasks.





