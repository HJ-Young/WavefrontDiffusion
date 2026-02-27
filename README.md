# WavefrontDiffusion: Dynamic Decoding Schedule for Improved Reasoning

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Paper](https://img.shields.io/badge/Paper-ICLR2026-blue)]([https://github.com/your-username/WavefrontDiffusion](https://openreview.net/pdf?id=4smJ6zY7vy))

Official implementation of the paper **"WavefrontDiffusion: Dynamic Decoding Schedule for Improved Reasoning"** (ICLR 2026).

---

## 💡 Overview

**WavefrontDiffusion** is a training-free dynamic scheduling strategy for Diffusion Language Models (DLMs). 

Traditional schedules like **Standard Diffusion** suffer from premature end-of-sequence predictions, while **BlockDiffusion** breaks coherent semantic units due to rigid boundaries. WavefrontDiffusion addresses these by:
- **Adaptive Expansion**: Dynamically expanding a "wavefront" of active tokens from finalized positions.
- **Context Completeness**: Ensuring tokens are only denoised when surrounded by sufficient contextual information.
- **Compute Parity**: Matching the computational cost (FLOPs) of block-based methods while delivering higher quality.

<!-- <p align="center">
  <img src="docs/illustration.png" width="800">
  <br><em>Figure: Comparison between Standard, Block, and Wavefront Diffusion scheduling.</em>
</p> -->

## 🚀 Main Results

WavefrontDiffusion achieves State-of-the-Art performance across reasoning and code generation benchmarks:

| Model | GSM8K (Acc) | MATH (Acc) | HumanEval (Pass@1) | BBH (Acc) |
| :--- | :---: | :---: | :---: | :---: |
| LLaDA-8B (Block) | 80.74 | 40.62 | 45.73 | 43.23 |
| **LLaDA-8B (Wavefront)** | **82.03** | **41.04** | **47.56** | **44.30** |

*All results obtained with a fixed budget of T=1024 steps.*

## 🛠️ Installation

```bash
# Clone the repository
git clone [https://github.com/HJ-Young/WavefrontDiffusion.git](https://github.com/HJ-Young/WavefrontDiffusion.git)
cd WavefrontDiffusion

# Environment setup (Python 3.9+, PyTorch 2.7.0+)
pip install -r requirements.txt
