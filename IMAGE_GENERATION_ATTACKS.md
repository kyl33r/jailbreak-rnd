# Image Generation Jailbreak Research

## Executive Summary

Recent research shows **60% attack success rate** on image generation models using Chain-of-Jailbreak (CoJ) attacks. This document summarizes attack methods for defensive research.

---

## 1. Chain-of-Jailbreak (CoJ) Attack

**Paper:** "Chain-of-Jailbreak Attack for Image Generation Models via Step by Step Editing" (ACL 2025)
**Authors:** Wang, Gao, Yuan, Huang, et al. (Tencent, CUHK)
**ArXiv:** arXiv:2410.03869

### The Attack Strategy

**Core Insight:** Single-shot malicious prompts get blocked. Breaking into multi-step sub-queries bypasses safety.

### Attack Process

```
Step 1: Start with benign image
        "Generate a person standing"

Step 2: Add harmful element 1  
        "Add a knife in their hand"

Step 3: Add harmful element 2
        "Make it more violent with blood"

Step 4: Final harmful image passes safety check
        (incremental changes bypass detection)
```

### Evaluation Results

| Model | Single Prompt ASR | CoJ Attack ASR |
|-------|-----------------|----------------|
| GPT-4V | ~14% | **60%** |
| GPT-4o | ~14% | **60%** |
| Gemini 1.5 | ~14% | **60%** |
| Gemini 1.5 Pro | ~14% | **60%** |

**Key Finding:** CoJ achieves **4x higher success** than single-prompt attacks.

### Defense: Think-Twice Prompting

The same paper proposes a simple defense:
- Before generating, analyze if final output matches any harm category
- **95% effective** at blocking CoJ attacks

---

## 2. TCBS-Attack (Token-level Constraint Boundary Search)

**Paper:** arXiv:2504.11106 (2025)

### Method

- Black-box attack requiring no model access
- Searches for adversarial tokens within semantic constraints
- Optimizes for both quality (CLIPScore) and bypass

### Results

| Model | ASR-4 | ASR-1 |
|-------|-------|-------|
| Stable Diffusion v1.4 | 92.5% | 82.0% |
| SafeGen | 75.0% | 74.0% |
| DALL-E 3 | 52.5% | 22.0% |

**ASR-4:** Attack succeeds if 4/4 judges agree it's harmful
**ASR-1:** Attack succeeds if 1/4 judges agrees

---

## 3. SneakyPrompt

**Paper:** IEEE Symposium on Security & Privacy 2024

- Black-box attack using reinforcement learning
- Searches for adversarial tokens that bypass safety
- Tested on DALL-E 2, Stable Diffusion

---

## 4. MMA-Diffusion

- White-box gradient-based attack
- Exploits diffusion model architecture
- High success but requires model access

---

## 5. Jailbreaking Prompt Attack (JPA)

**Paper:** arXiv:2404.02928

- Controllable adversarial attack
- Can specify attack intensity
- Tested on SDXL, DALL-E 2, Midjourney

---

## Attack Surface Analysis

### Why Image Models Are Vulnerable

1. **Iterative Generation**: Diffusion models refine images step-by-step
2. **Safety Check Timing**: Often only checks final output, not intermediate steps
3. **Compositionality**: Combining benign elements can create harmful image
4. **Latent Space**: Adversarial perturbations in latent space hard to detect

### Vulnerability Timeline

```
Initial Prompt → Safety Check → BLOCKED
                         ↓
Benign Start → Incremental Edits → Safety Check → PASSED
                         ↓
Final Harmful Image → Delivered to User
```

---

## Defense Strategies

### 1. Think-Twice Prompting (Recommended)
- Analyze full editing chain before generation
- Check final intent matches safety policy
- 95% block rate against CoJ

### 2. Intermediate Safety Checks
- Check after each editing step, not just final
- Detect gradual intent escalation

### 3. Semantic Filtering
- Analyze semantic intent at each step
- Flag if chain leads to harmful category

### 4. Output Moderation
- Post-generation content filtering
- Additional safety layer

---

## Code & Datasets

- **CoJ-Bench**: Dataset with 9 safety scenarios
- Official implementations in paper supplements

---

## Key Takeaways

1. **Multi-step attacks** (CoJ) are 4x more effective than single prompts
2. **Defenses exist**: Think-Twice achieves 95% block rate
3. **All major models affected**: GPT-4V, DALL-E, Stable Diffusion, Gemini
4. **Research is evolving**: New attacks discovered regularly