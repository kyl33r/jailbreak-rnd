# Jailbreak Attack Taxonomy

This document classifies jailbreak research papers by their approach category, showing the landscape of current trends in LLM jailbreaking.

---

## Overview

Jailbreak attacks on LLMs can be classified into several major categories based on their methodology, attack vector, and target. This taxonomy categorizes the research landscape.

---

## Category 1: Optimization-Based Attacks

**Approach:** Treats jailbreak as an optimization problem to find adversarial tokens/suffixes that trigger harmful generation.

### Foundational Work

| Paper | Key Innovation | Target Access |
|-------|----------------|--------------|
| GCG (Zou et al., 2023) | First gradient-based discrete token optimization | White-box |
| Faster-GCG (Li et al., 2024) | 10x efficiency improvement | White-box |
| I-GCG (Jia et al., 2024) | Near 100% ASR with improved techniques | White-box |
| ADC (Liu et al., 2024) | Dense-to-sparse constrained optimization | White-box |
| AttnGCG (Wang et al., 2024) | Attention manipulation enhancement | White-box |

### Transferable & Universal

| Paper | Key Innovation | Target Access |
|-------|----------------|--------------|
| AmpleGCG (LIAO & SUN, 2024) | Generative model of adversarial suffixes | White-box → Black-box transfer |
| Mask-GCG (Mu et al., 2025) | Token masking for efficient attacks | White-box |
| Resurgence of GCG (2025) | Systematic GCG across model scales | White-box |

### Key Characteristics

- **Requires:** Gradient access (white-box) or trained substitute models
- **Strength:** Highly effective (>90% ASR on many models)
- **Weakness:** Computationally expensive, requires access
- **Trend:** Moves toward efficiency and transferability

---

## Category 2: LLM-Generated Attacks

**Approach:** Uses an auxiliary LLM to generate/refine jailbreak prompts iteratively.

### Papers

| Paper | Method | Target Access |
|-------|--------|--------------|
| PAIR (Chao et al., 2023) | Iterative refinement with feedback | Black-box |
| AutoDAN (Liu et al., 2024) | LLM generates stealthy prompts | Black-box |
| J2: Jailbreaking to Jailbreak (Kritz et al., 2025) | Use refusal-trained models as attackers | Black-box |
| AutoAdv (Reddy et al., 2025) | Multi-turn automated prompting | Black-box |
| Crescento (Russinovich, 2025) | Multi-turn escalation | Black-box |

### Key Characteristics

- **Requires:** Only input-output API access
- **Strength:** Works on closed APIs, no internal access needed
- **Weakness:** Query efficiency varies, requires multiple attempts
- **Trend:** Increasing automation and sophistication

---

## Category 3: Hardware/Fault Injection Attacks

**Approach:** Exploits physical/hardware vulnerabilities rather than prompt manipulation.

### Papers

| Paper | Method | Target Access |
|-------|--------|--------------|
| PRISONBREAK (2024) | Rowhammer bit-flip attacks | Physical access |

### Key Characteristics

- **Requires:** Physical hardware access
- **Strength:** Bypasses all software defenses
- **Weakness:** Requires specialized hardware setup
- **Trend:** Growing area of concern for secure deployment

---

## Category 4: Black-Box/API Attacks

**Approach:** Attacks that work with only output token access, no gradients or internal state.

### Papers

| Paper | Method | Target Access |
|-------|--------|--------------|
| VERA (2025) | Variational inference framework | API-only |
| JULI (Wang et al., 2025) | Token log probability exploitation | API + log probs |
| Adversarial Reasoning (Sabbaghi et al., 2025) | Reasoning-guided search | Black-box |
| Faster-GCG transfer | Transfer from open-source | API-only |

### Key Characteristics

- **Requires:** API token generation
- **Strength:** Works on API-only models
- **Weakness:** Less efficient than white-box
- **Trend:** Increasingly sophisticated despite limitations

---

## Category 5: Multi-Turn/Conversational Attacks

**Approach:** Uses multiple conversation turns to gradually bypass safety guardrails.

### Papers

| Paper | Method |
|-------|--------|
| Crescento (Russinovich, 2025) | Gradual escalation |
| AutoAdv (Reddy et al., 2025) | Multi-turn auto-refinement |
| PAIR (Chao et al., 2023) | Iterative refinement |

### Key Characteristics

- **Requires:** Conversational API
- **Strength:** Effective on models resistant to single-turn
- **Weakness:** Longer attack time
- **Trend:** Growing importance as primary defense layer

---

## Category 6: Novel Mechanism Attacks

**Approach:** Targets specific model mechanisms rather than prompts.

### Papers

| Paper | Method |
|-------|--------|
| Don't Say No (Zhou et al., 2024) | Suppress refusal capability |
| Catastrophic Jailbreak (Huang et al., 2024) | Exploit generation process |
| Involuntary Jailbreak (2024) | Model truth-telling failure |

### Key Characteristics

- **Target:** Internal model mechanisms
- **Strength:** May bypass multiple defenses
- **Weakness:** Model-specific
- **Trend:** Understanding model internals

---

## Category 7: Benchmarks & Evaluation Frameworks

**Approach:** Provides infrastructure for evaluating jailbreak attacks/defenses.

### Papers

| Paper | Focus |
|-------|-------|
| JailbreakBench (Chao et al., 2024) | Open robustness benchmark |
| JailbreakRadar (Chu et al., 2024) | Comprehensive assessment |
| h4rm3l (Andriushchenko et al., 2024) | Dynamic composable attacks |
| MLCommons v0.5 (2025) | Industry benchmark |

### Key Characteristics

- **Purpose:** Standardized evaluation
- **Components:** Datasets, metrics, leaderboards
- **Importance:** Reproducibility, progress tracking

---

## Category 8: Defense Research

**Approach:** Methods to defend against jailbreak attacks.

### Papers

| Paper | Defense Method | Effectiveness |
|-------|--------------|-------------|
| ProEAT (2025) | Adversarial training | +34% improvement |
| Llama Guard | Safety-tuned model | Evaluator benchmark |

### Key Characteristics

- **Approach:** Training-based, detection-based
- **Limitation:** Not complete solution
- **Trend:** Growing area of concern

---

## Research Trend Analysis

### Evolution of Attack Capabilities

```
2019-2021: Manual prompt engineering
    ↓
2022-2023: Gradient-based optimization (GCG)
    ↓
2023-2024: LLM-generated attacks
    ↓
2024-2025: Black-box & multi-turn attacks
    ↓
2025+: Hardware attacks, reasoning-based
```

### Key Trends

1. **Automation**: Moving from manual to fully automated
2. **Access Reduction**: White-box → Black-box → API-only
3. **Defense Arms Race**: New attacks → New defenses → New attacks
4. **Transferability**: Open-source attacks → closed APIs
5. **Complexity**: Single-turn → Multi-turn conversations

### Most Effective Approaches (by Category)

| Category | ASR (typical) | Practicality |
|----------|---------------|-------------|
| Optimization (GCG) | 90-100% | Requires access |
| LLM-generated | 70-95% | API accessible |
| Multi-turn | 80-95% | Conversational API |
| Black-box | 40-80% | API-only |

---

## Attack Success Rates by Model Type

### Open-Source Models

| Attack | Llama-2 | Vicuna | Mistral | Claude |
|--------|---------|--------|--------|-------|
| GCG | 53-96% | Variable | - | - |
| ADC | 96% | 80%+ | - | - |
| AmpleGCG | ~100% | ~100% | - | - |

### Closed-Source APIs

| Attack | GPT-3.5 | GPT-4 | Claude | Gemini |
|--------|--------|------|-------|--------|
| PAIR | High | Moderate | - | - |
| Crescento | High | High | Moderate | High |
| AutoDAN | 99% | - | - | - |

---

## Summary

The jailbreak research landscape shows:

1. **Diverse Approaches**: From gradient optimization to conversational attacks
2. **Reducing Access Requirements**: Attacks work with less information
3. **Increasing Effectiveness**: New methods achieve high success rates
4. **Defense Challenge**: Current defenses are partial solutions
5. **Transferability**: Key finding that open-source attacks transfer to closed APIs

---

## References

- See `research/` directory for individual paper summaries
- See `RESEARCH.md` for complete paper list with citations