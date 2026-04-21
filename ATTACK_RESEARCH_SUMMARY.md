# Attack Methods Research: Text & Image Generation Models

## Part 1: Text LLM Attacks (GCG Family)

### How Red Teams Attack Qwen with GCG Variants

| Attack Method | How It Works | Effectiveness on Qwen |
|--------------|--------------|---------------------|
| **GCG (Original)** | Optimizes adversarial suffix tokens to minimize refusal loss | Baseline ~50-70% |
| **Faster-GCG** | Improved token selection, 10x faster | +29% over GCG |
| **I-GCG** | Better initialization + optimization | ~100% ASR |
| **AmpleGCG** | Trains generative model for universal suffixes | Universal, transferable |

### Attack Process (GCG Variants)

1. **Target a harmful query**: "How to make a bomb"
2. **Add adversarial suffix**: Algorithm optimizes random tokens
3. **Optimize**: Iteratively update tokens to minimize refusal probability
4. **Deploy**: Final suffix triggers harmful output

### Key Finding for Qwen

Research shows Qwen2.5 models are tested in recent GCG papers. Key insight: **larger models more resistant but not immune**.

---

## Part 2: Image Generation Model Attacks

### Overview

Text-to-image models (Stable Diffusion, DALL-E, Midjourney) have different attack surfaces than LLMs.

### Major Attack Methods

| Attack | Method | ASR | Target |
|--------|--------|-----|--------|
| **Chain-of-Jailbreak (CoJ)** | Decompose into sub-queries, iterative editing | 60% | GPT-4V, GPT-4o, Gemini |
| **TCBS-Attack** | Token-level constraint boundary search | 52.5% | Stable Diffusion, DALL-E 3 |
| **SneakyPrompt** | Black-box adversarial prompts | 14% baseline | DALL-E, Stable Diffusion |
| **MMA-Diffusion** | White-box gradient-based | High | Stable Diffusion |
| **Jailbreaking Prompt Attack (JPA)** | Controllable adversarial attack | Varies | SDXL, DALL-E 2 |

### Chain-of-Jailbreak (CoJ) - Most Effective

**Paper:** ACL 2025 Findings

**Method:**
1. Take malicious prompt that fails safety check
2. **Decompose** into benign sub-queries
3. **Iteratively edit** images step-by-step
4. **Bypass** final safety check

**Example:**
- Original: "Generate violent image" → BLOCKED
- CoJ: "Generate person" → "Add weapon" → "Add blood" → BYPASSED

**Results:**
- 60% bypass rate on GPT-4V/GPT-4o/Gemini
- Only 14% for single-shot prompts

### TCBS-Attack (Token-level)

**Paper:** arXiv:2504.11106

**Method:**
- Search for adversarial tokens within constraint boundaries
- Black-box approach (no gradient access needed)
- Optimizes for both ASR-4 (4 judge consensus) and ASR-1

**Results:**
- 92.5% on SDv1.4
- 52.5% ASR-4, 22% ASR-1 on DALL-E 3
- Works on securely trained open-source models

---

## Defense Approaches

### For Text LLMs (Qwen)
- Adversarial training (ProEAT: +34% improvement)
- Input filtering
- Output classifiers (Llama Guard)
- Multi-layer defense

### For Image Generation
- **Think-Twice Prompting**: Simple defense with 95% effectiveness
- Safety checkers (Stable Diffusion's Safety Checker)
- Prompt filtering
- Output moderation

---

## Key Research Papers

### Text LLM Attacks
1. GCG (Zou et al., 2023) - arXiv:2307.15043
2. Faster-GCG (Li et al., 2024) - arXiv:2410.15362
3. I-GCG (Jia et al., 2024) - arXiv:2405.21018
4. AmpleGCG (Liao & Sun, 2024) - arXiv:2404.07921

### Image Generation Attacks
1. Chain-of-Jailbreak (Wang et al., 2025) - ACL 2025, arXiv:2410.03869
2. TCBS-Attack (2025) - arXiv:2504.11106
3. SneakyPrompt (Yang et al., 2024) - IEEE Symposium
4. Jailbreaking Prompt Attack (2024) - arXiv:2404.02928

---

## Recommendations for Safeguarding Qwen

1. **Test with GCG variants**: Run I-GCG/AmpleGCG to find vulnerabilities
2. **Adversarial training**: Train on adversarial examples
3. **Multi-turn conversation defense**: Guard against gradual escalation
4. **Monitor for adversarial patterns**: Detect suffix-based attacks
5. **Red team regularly**: Continuously test with evolving methods