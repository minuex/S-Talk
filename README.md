# 기초프로젝트


This model performs voice recognition and speaker separation by streaming the conversational voice in real time during an encounter with the other person, converts the voice into text, and inputs the conversation content for each speaker into llama3. This provides a function that recommends the next topic when the atmosphere becomes awkward based on analysis of conversation content.


![structure](https://github.com/minuex/S-Talk/blob/main/전체구조도.jpg)

---
## Installation

---
## model used
### 1. Wespeaker

WeSpeaker is a research and production-oriented toolkit designed for learning speaker embeddings, which are fixed-dimensional vector representations used in tasks such as speaker recognition and diarization. This toolkit implements state-of-the-art speaker embedding models, loss functions, and scoring backends to deliver competitive results.

1. Competitive Results: Achieves highly competitive performance on datasets like VoxCeleb, CNCeleb, and VoxConverse, replicating tricks from winning systems in speaker verification challenges to enhance system performance.
2. Lightweight: Built on PyTorch and its ecosystem without dependencies on external tools like Kaldi.
3. Unified IO (UIO): Introduces the unified IO system from Wenet, providing a seamless interface to support hundreds of millions of hours of data.
4. Real-time Feature Preparation: Performs data augmentation and feature extraction in real-time, reducing disk costs and improving model robustness.
5. Distributed Learning: Supports multi-node, multi-GPU scaling using Pytorch’s DistributedDataParallel.
6. Production Ready: Easily exportable to formats like torch JIT or ONNX for deployment in production environments.

[WESPEAKER: A RESEARCH AND PRODUCTION ORIENTED SPEAKER EMBEDDING LEARNING TOOLKIT](https://arxiv.org/pdf/2210.17016)
![structure](https://github.com/minuex/S-Talk/blob/main/wespeaker%20구조도.jpg)

### 2. Whisper


### 3. Llama3

LLAMA3 models by Meta in April 2024, which have been pre-trained on over 15 trillion tokens, demonstrate impressive performance. The research investigates the effectiveness of low-bit quantization for these models, a technique critical for deploying LLMs in resource-limited environments.

#### Track1: Post-Training Quantization
We evaluated the performance of LLAMA3-8B and LLAMA3-70B using eight different PTQ methods, covering a range of bit widths from 1 to 8 bits. Even at ultra-low bit widths, the accuracy of quantized LLAMA3-8B remained high, with binarized LLM quantization methods showing superior performance compared to GPTQ, AWQ, and QuIP. Evaluation of quantized activations using SmoothQuant was also conducted. Additionally, the LLAMA3-70B model exhibited significant robustness across different quantization methods.

#### Track2: LoRA-FineTuning Quantization
we evaluated the performance of 4-bit LLAMA3-8B using two different LoRA-FT quantization methods: QLoRA and IR-QLoRA. it was observed that low-rank fine-tuning on the Alpaca dataset under LoRA-FT quantization not only failed to compensate for quantization errors but exacerbated performance degradation. This contrasts with similar phenomena observed in LLAMA1 and LLAMA2, where low-rank finetuned quantized versions could surpass the original FP16 counterpart.  Despite this, 4-bit LoRA-FT quantized LLAMA3-8B outperformed LLAMA1-7B and LLAMA2-7B significantly.

LLAMA3 models suffer from notable performance degradation when quantized to ultra-low bit widths. This underlines a significant gap in the current capabilities of low-bit quantization methods and the actual performance needs. 

[How Good Are Low-bit Quantized LLAMA3 Models? An Empirical Study](https://arxiv.org/pdf/2404.14047)


....(+내용 추가 예정)

---


