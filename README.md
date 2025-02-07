# Jarvis-R1
<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable html -->
<!-- markdownlint-disable no-duplicate-header -->

<div align="center">
  <img src="https://github.com/JARVIS-SOL/JARVIS/blob/main/image/jarvis_banner.png?raw=true" width="100%" alt="Jarvis-deepseek-V3" />
</div>
<hr>
<div align="center" style="line-height: 1;">
  <a href="https://jarvisonsol.xyz/" target="_blank" style="margin: 2px;">
    <img alt="Homepage" src="https://github.com/JARVIS-SOL/JARVIS/blob/main/image/badge.svg?raw=true" width="20%" style="display: inline-block; vertical-align: middle;"/>
  </a>
  <a href="https://jarvisonsol.xyz/" target="_blank" style="margin: 2px;">
    <img alt="Homepage" src="https://github.com/JARVIS-SOL/JARVIS/blob/main/image/twitter.svg?raw=true" width="20%" style="display: inline-block; vertical-align: middle;"/>
  </a>
  
  
</div>




</div>

## 0. Demo

Experience JARVIS in action! Try our online demo at   [https://jarvisonsol.xyz](https://jarvisonsol.xyz)


## 1. Introduction

In the rapidly evolving landscape of artificial intelligence, Deepseek has emerged as a true pioneer, pushing the boundaries of what's possible in natural language processing and understanding. With its groundbreaking advancements in machine learning and neural networks, Deepseek has set new standards for AI capabilities, offering unparalleled depth and nuance in language comprehension and generation.

Deepseek's innovative approach combines cutting-edge algorithms with vast knowledge bases, resulting in an AI system that not only processes information but truly understands context, intent, and the subtleties of human communication. Its ability to grasp complex concepts, reason logically, and generate human-like responses has revolutionized the field of AI, opening up new possibilities for human-AI interaction.

Building upon this remarkable foundation, we are witnessing a transformation in software as revolutionary as the invention of paper - a breakthrough that didn't just innovate but fundamentally accelerated the spread of human knowledge. In the same way, modern AI, exemplified by Deepseek's achievements, is now reshaping how we build and interact with software, unlocking meaning at a scale never before possible.

This revolution isn't about faster processors or cleverer algorithms. It's about understanding. For the first time, AI agents can process and generate human-like semantics at scale, transforming rigid, task-specific programs into systems that adapt to context with astonishing fluidity.

Everything we know about software is being redefined.

Tasks that once demanded painstakingly intricate code - interpreting natural language, analyzing images, or crafting human-like responses - can now be achieved with simple prompts and orchestration logic. The age-old struggle of bending strict logic to handle the fluidity of meaning is over. The rules no longer need to be written; they can now be described.

What's truly transformative is how seamlessly these capabilities fit into today's cloud-native architectures. The modularity, scalability, and efficiency that drive microservices are perfectly aligned for deploying swarms of intelligent agents. While LLMs require specialized infrastructure, agents demand only a shift in perspective.

The wave has already begun, first in the cloud, but soon it will cascade to edge devices, robotics, and decentralized networks. Not as some sci-fi dream of artificial life, but as practical, context-aware tools that elevate how we work and interact with technology.

This is why we created JARVIS - the first personal assistant based on Deepseek.

Just as paper once fueled a cultural renaissance, AI is igniting the next great leap forward. Join us, and let's shape the future together.

We introduce our first-generation reasoning models, Jarvis-R1-Zero and Jarvis-R1. 
Jarvis-R1-Zero, a model trained via large-scale reinforcement learning (RL) without supervised fine-tuning (SFT) as a preliminary step, demonstrated remarkable performance on reasoning.
With RL, Jarvis-R1-Zero naturally emerged with numerous powerful and interesting reasoning behaviors.
However, Jarvis-R1-Zero encounters challenges such as endless repetition, poor readability, and language mixing. To address these issues and further enhance reasoning performance,
we introduce Jarvis-R1, which incorporates cold-start data before RL.
Jarvis-R1 achieves performance comparable to OpenAI-o1 across math, code, and reasoning tasks. 
To support the research community, we have open-sourced Jarvis-R1-Zero, Jarvis-R1, and six dense models distilled from Jarvis-R1 based on Llama and Qwen. Jarvis-R1-Distill-Qwen-32B outperforms OpenAI-o1-mini across various benchmarks, achieving new state-of-the-art results for dense models.



<p align="center">
  <img width="80%" src="https://github.com/JARVIS-SOL/JARVIS/blob/main/image/benchmark1.jpg?raw=true">
</p>

## 2. Model Summary

---

**Post-Training: Large-Scale Reinforcement Learning on the Base Model**

-  We directly apply reinforcement learning (RL) to the base model without relying on supervised fine-tuning (SFT) as a preliminary step. This approach allows the model to explore chain-of-thought (CoT) for solving complex problems, resulting in the development of Jarvis-R1-Zero. Jarvis-R1-Zero demonstrates capabilities such as self-verification, reflection, and generating long CoTs, marking a significant milestone for the research community. Notably, it is the first open research to validate that reasoning capabilities of LLMs can be incentivized purely through RL, without the need for SFT. This breakthrough paves the way for future advancements in this area.

-   We introduce our pipeline to develop Jarvis-R1. The pipeline incorporates two RL stages aimed at discovering improved reasoning patterns and aligning with human preferences, as well as two SFT stages that serve as the seed for the model's reasoning and non-reasoning capabilities.
    We believe the pipeline will benefit the industry by creating better models. 

---

**Distillation: Smaller Models Can Be Powerful Too**

-  We demonstrate that the reasoning patterns of larger models can be distilled into smaller models, resulting in better performance compared to the reasoning patterns discovered through RL on small models. The open source Jarvis-R1, as well as its API, will benefit the research community to distill better smaller models in the future. 
- Using the reasoning data generated by Jarvis-R1, we fine-tuned several dense models that are widely used in the research community. The evaluation results demonstrate that the distilled smaller dense models perform exceptionally well on benchmarks. We open-source distilled 1.5B, 7B, 8B, 14B, 32B, and 70B checkpoints based on Qwen2.5 and Llama3 series to the community.

## 3. Model Downloads

### Jarvis-R1 Models

<div align="center">

| **Model** | **#Total Params** | **#Activated Params** | **Context Length** | **Download** |
| :------------: | :------------: | :------------: | :------------: | :------------: |
| Jarvis-R1-Zero | 671B | 37B | 128K   | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1-Zero)   |
| Jarvis-R1   | 671B | 37B |  128K   | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1)   |

</div>

Jarvis-R1-Zero & Jarvis-R1 are trained based on DeepSeek-V3-Base. 
For more details regarding the model architecture, please refer to [DeepSeek-V3](https://github.com/deepseek-ai/DeepSeek-V3) repository.

### Jarvis-R1-Distill Models

<div align="center">

| **Model** | **Base Model** | **Download** |
| :------------: | :------------: | :------------: |
| Jarvis-R1-Distill-Qwen-1.5B  | [Qwen2.5-Math-1.5B](https://huggingface.co/Qwen/Qwen2.5-Math-1.5B) | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1-Distill-Qwen-1.5B)   |
| Jarvis-R1-Distill-Qwen-7B  | [Qwen2.5-Math-7B](https://huggingface.co/Qwen/Qwen2.5-Math-7B) | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1-Distill-Qwen-7B)   |
| Jarvis-R1-Distill-Llama-8B  | [Llama-3.1-8B](https://huggingface.co/meta-llama/Llama-3.1-8B) | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1-Distill-Llama-8B)   |
| Jarvis-R1-Distill-Qwen-14B   | [Qwen2.5-14B](https://huggingface.co/Qwen/Qwen2.5-14B) | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1-Distill-Qwen-14B)   |
|Jarvis-R1-Distill-Qwen-32B  | [Qwen2.5-32B](https://huggingface.co/Qwen/Qwen2.5-32B) | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1-Distill-Qwen-32B)   |
| Jarvis-R1-Distill-Llama-70B  | [Llama-3.3-70B-Instruct](https://huggingface.co/meta-llama/Llama-3.3-70B-Instruct) | [HuggingFace](https://huggingface.co/deepseek-ai/Jarvis-R1-Distill-Llama-70B)   |

</div>

Jarvis-R1-Distill models are fine-tuned based on open-source models, using samples generated by Jarvis-R1.
We slightly change their configs and tokenizers. Please use our setting to run these models.

## 4. Evaluation Results

### Jarvis-R1-Evaluation
 For all our models, the maximum generation length is set to 32,768 tokens. For benchmarks requiring sampling, we use a temperature of $0.6$, a top-p value of $0.95$, and generate 64 responses per query to estimate pass@1.
<div align="center">


| Category | Benchmark (Metric) | Claude-3.5-Sonnet-1022 | GPT-4o 0513 | DeepSeek V3 | OpenAI o1-mini | OpenAI o1-1217 | Jarvis R1 |
|----------|-------------------|----------------------|------------|--------------|----------------|------------|--------------|
| | Architecture | - | - | MoE | - | - | MoE |
| | # Activated Params | - | - | 37B | - | - | 37B |
| | # Total Params | - | - | 671B | - | - | 671B |
| English | MMLU (Pass@1) | 88.3 | 87.2 | 88.5 | 85.2 | **91.8** | 90.8 |
| | MMLU-Redux (EM) | 88.9 | 88.0 | 89.1 | 86.7 | - | **92.9** |
| | MMLU-Pro (EM) | 78.0 | 72.6 | 75.9 | 80.3 | - | **84.0** |
| | DROP (3-shot F1) | 88.3 | 83.7 | 91.6 | 83.9 | 90.2 | **92.2** |
| | IF-Eval (Prompt Strict) | **86.5** | 84.3 | 86.1 | 84.8 | - | 83.3 |
| | GPQA-Diamond (Pass@1) | 65.0 | 49.9 | 59.1 | 60.0 | **75.7** | 71.5 |
| | SimpleQA (Correct) | 28.4 | 38.2 | 24.9 | 7.0 | **47.0** | 30.1 |
| | FRAMES (Acc.) | 72.5 | 80.5 | 73.3 | 76.9 | - | **82.5** |
| | AlpacaEval2.0 (LC-winrate) | 52.0 | 51.1 | 70.0 | 57.8 | - | **87.6** |
| | ArenaHard (GPT-4-1106) | 85.2 | 80.4 | 85.5 | 92.0 | - | **92.3** |
| Code | LiveCodeBench (Pass@1-COT) | 33.8 | 34.2 | - | 53.8 | 63.4 | **65.9** |
| | Codeforces (Percentile) | 20.3 | 23.6 | 58.7 | 93.4 | **96.6** | 96.3 |
| | Codeforces (Rating) | 717 | 759 | 1134 | 1820 | **2061** | 2029 |
| | SWE Verified (Resolved) | **50.8** | 38.8 | 42.0 | 41.6 | 48.9 | 49.2 |
| | Aider-Polyglot (Acc.) | 45.3 | 16.0 | 49.6 | 32.9 | **61.7** | 53.3 |
| Math | AIME 2024 (Pass@1) | 16.0 | 9.3 | 39.2 | 63.6 | 79.2 | **79.8** |
| | MATH-500 (Pass@1) | 78.3 | 74.6 | 90.2 | 90.0 | 96.4 | **97.3** |
| | CNMO 2024 (Pass@1) | 13.1 | 10.8 | 43.2 | 67.6 | - | **78.8** |
| Chinese | CLUEWSC (EM) | 85.4 | 87.9 | 90.9 | 89.9 | - | **92.8** |
| | C-Eval (EM) | 76.7 | 76.0 | 86.5 | 68.9 | - | **91.8** |
| | C-SimpleQA (Correct) | 55.4 | 58.7 | **68.0** | 40.3 | - | 63.7 |

</div>


### Distilled Model Evaluation


<div align="center">

| Model                                    | AIME 2024 pass@1 | AIME 2024 cons@64 | MATH-500 pass@1 | GPQA Diamond pass@1 | LiveCodeBench pass@1 | CodeForces rating |
|------------------------------------------|------------------|-------------------|-----------------|----------------------|----------------------|-------------------|
| GPT-4o-0513                          | 9.3              | 13.4              | 74.6            | 49.9                 | 32.9                 | 759               |
| Claude-3.5-Sonnet-1022             | 16.0             | 26.7                 | 78.3            | 65.0                 | 38.9                 | 717               |
| o1-mini                              | 63.6             | 80.0              | 90.0            | 60.0                 | 53.8                 | **1820**          |
| QwQ-32B-Preview                              | 44.0             | 60.0                 | 90.6            | 54.5               | 41.9                 | 1316              |
| Jarvis-R1-Distill-Qwen-1.5B       | 28.9             | 52.7              | 83.9            | 33.8                 | 16.9                 | 954               |
| Jarvis-R1-Distill-Qwen-7B          | 55.5             | 83.3              | 92.8            | 49.1                 | 37.6                 | 1189              |
| Jarvis-R1-Distill-Qwen-14B         | 69.7             | 80.0              | 93.9            | 59.1                 | 53.1                 | 1481              |
| Jarvis-R1-Distill-Qwen-32B        | **72.6**         | 83.3              | 94.3            | 62.1                 | 57.2                 | 1691              |
| Jarvis-R1-Distill-Llama-8B         | 50.4             | 80.0              | 89.1            | 49.0                 | 39.6                 | 1205              |
| Jarvis-R1-Distill-Llama-70B        | 70.0             | **86.7**          | **94.5**        | **65.2**             | **57.5**             | 1633              |

</div>

