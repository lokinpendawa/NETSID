# Netsid: A Portable Neuro-Symbolic AI Framework for Prolog Ecosystems

**Author:** Teddy (lokinpendawa)  
**Date:** November 2026  
**Status:** Experimental / Proof of Concept

---

## 1. Background: Bridging Two Worlds

Modern AI is dominated by massive black-box models that require expensive GPUs and vast amounts of data. While effective for perception tasks, they struggle with **logical reasoning** and **explainability**. Conversely, **Prolog** excels at symbolic reasoning and expert systems but lacks efficient numerical computation for heavy matrix operations.

**Netsid** was born from a simple question: *What if we combine the computational speed of Rust with the reasoning power of Prolog, in a lightweight and portable framework?*

---

## 2. Architecture: Hybrid Neuro-Symbolic

Netsid combines two core engines:

- **Rust (Data Plane):** Handles heavy computation: Tensors, MatMul (AVX2), Softmax, Broadcast, GELU, Cross Entropy, Autograd, Adam Optimizer, Char-CNN, Self-Attention, L2 Regulation, Cosine Similarity, and Euclidean Distance.
- **Prolog (Control Plane):** Handles logic: DCG Parser (NLP), Training Orchestration, and Memory Management.
- **FFI Bridge:** Two-way communication between Rust and Prolog. Prolog sends commands (e.g., *"Multiply Tensor A and B"*), Rust executes them, and returns the result.

```text
[Input Data] 
     ↓
[Prolog: DCG Parser & Logic Rules] 
     ↓
[Rust: Tensor, Autograd, SIMD, and Other] 
     ↓
[Output: Prediction / Intent / Verdict]
