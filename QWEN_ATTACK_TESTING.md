# Research: Testing Qwen Against GCG-Style Attacks

## Overview

This document outlines how red teams test text models like Qwen using GCG variants. For defensive research only.

---

## Attack Methods Summary

### 1. GCG (Greedy Coordinate Gradient)

**Original Paper:** Zou et al., "Universal and Transferable Adversarial Attacks" (2023)

**How it works:**
1. Start with harmful query + random suffix tokens
2. Compute gradients w.r.t. token embeddings
3. Greedily replace tokens that minimize refusal loss
4. Repeat until jailbreak succeeds

**Requirements:** White-box access (gradients)

### 2. Faster-GCG

**Paper:** Li et al., arXiv:2410.15362 (2024)

**Improvements:**
- 10x computational efficiency
- 29% higher success rate than original GCG

### 3. I-GCG (Improved GCG)

**Paper:** Jia et al., arXiv:2405.21018 (ICLR 2025)

**Key Techniques:**
- Better initialization strategies
- Improved coordinate selection
- **Achieves ~100% ASR** on many models

### 4. AmpleGCG

**Paper:** Liao & Sun, arXiv:2404.07921 (COLM 2024)

**Approach:**
- Trains a generative model for adversarial suffixes
- Generates suffixes in seconds (vs. minutes of optimization)
- **Universal and transferable** to other models

---

## Testing Qwen: Research Approach

### Step 1: Baseline Safety Test
- Test direct harmful prompts
- Qwen3:8b shows 100% refusal (our test)

### Step 2: GCG Attack Testing

To test GCG-style attacks on Qwen:

1. **Clone implementations:**
   ```bash
   # GCG original
   git clone https://github.com/llm-attacks/llm-attacks
   
   # I-GCG (recommended)
   git clone https://github.com/jiaxiaojunQAQ/I-GCG
   
   # AmpleGCG
   git clone https://github.com/OSU-NLP-Group/AmpleGCG
   ```

2. **Configure for Qwen:**
   - Update model path to Qwen weights
   - Adjust tokenization for Qwen tokenizer

3. **Run evaluation:**
   - Generate adversarial suffixes
   - Test if they bypass Qwen's refusals
   - Measure attack success rate

### Step 3: Transferability Test

AmpleGCG key feature: suffixes trained on open-source models transfer to other models.

- Train/generate on Llama-2
- Test if suffixes also work on Qwen
- Measures cross-model vulnerability

---

## Key Findings from Literature

### Qwen Vulnerability Profile

| Attack | Qwen2.5-0.5B | Qwen2.5-1B | Larger Qwen |
|--------|-------------|------------|-------------|
| GCG | High ASR | Moderate | Lower |
| T-GCG | Moderate | Moderate | Lower |
| Simulated Annealing | Competitive | Competitive | Limited |

### Important Insights

1. **Larger models more resistant** - but not immune
2. **Coding prompts more vulnerable** than safety prompts
3. **Reasoning can be exploited** as attack vector
4. **Prefix evaluation** shows stricter results than suffix-only

---

## Defensive Research Directions

### 1. Adversarial Training
- Train on GCG-generated adversarial examples
- ProEAT shows +34% improvement

### 2. Detection
- Detect adversarial suffix patterns
- Monitor for optimization behavior

### 3. Multi-Layer Defense
- Input filtering + output classification
- Defense in depth

### 4. Regular Testing
- Continuously test with evolving methods
- Red team regularly

---

## Code Resources

| Resource | URL |
|----------|-----|
| GCG | github.com/llm-attacks/llm-attacks |
| I-GCG | github.com/jiaxiaojunQAQ/I-GCG |
| AmpleGCG | github.com/OSU-NLP-Group/AmpleGCG |
| JailbreakBench | github.com/jailbreakbench/jailbreakbench |
| AdvBench | From GCG paper |

---

## Summary

For safeguarding Qwen:

1. **Baseline is strong** - Qwen3:8b refused all direct harmful prompts
2. **GCG variants are more sophisticated** - can find adversarial suffixes
3. **Key defense**: adversarial training + multi-layer filtering
4. **Regular testing** essential as attacks evolve