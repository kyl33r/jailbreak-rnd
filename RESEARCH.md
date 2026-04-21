# Jailbreaking Open Source LLMs: Research Survey

This document summarizes key whitepapers and research on adversarial jailbreak attacks against open source large language models.

## Overview

Jailbreak attacks bypass safety guardrails in LLMs to elicit harmful or undesired outputs. Research has demonstrated that both open-source and closed-source models remain vulnerable to various attack vectors, even after safety alignment.

---

## Key Whitepapers & Research

### 1. MLCommons Jailbreak Benchmark v0.5

**Reference:** MLCommons AI Literacy Security Working Group. "Introducing v0.5 of the Jailbreak Benchmark." October 2025.

**Summary:** Comprehensive benchmark evaluating jailbreak resistance across text-to-text LLMs and text+image-to-text VLMs. Tests systems against various jailbreak tactics in realistic black-box settings. Findings show jailbreaks are still discovered at alarming rates even for frontier models.

---

### 2. JailbreakBench: An Open Robustness Benchmark for Jailbreaking LLMs

**Authors:** Patrick Chao, Edoardo Debenedetti, Alexander Robey, Maksym Andriushchenko, et al.

**ArXiv:** arXiv:2404.01318 (2024)

**Reference:** https://github.com/jailbreakbench/jailbreakbench

**Summary:** Open-sourced benchmark with evolving repository of state-of-the-art jailbreak prompts, evaluation code, and leaderboard. Identifies Llama Guard as preferable jailbreaking evaluator. Both open and closed-source LLMs remain susceptible to jailbreaking attacks that can be mitigated but not eliminated by existing defenses.

---

### 3. ADC: Adaptive Dense-to-sparse Constrained Optimization

**Authors:** Qi Liu, et al.

**ArXiv:** arXiv:2405.09113 (2024)

**Summary:** Novel token-level attack method that successfully jailbreaks multiple open-source LLMs. Achieves 96.2% attack success rate on Llama2-chat-7B, surpassing other methods by significant margins. Demonstrates vulnerability of even adversarially trained models (Zephyr-R2D2).

---

### 4. PRISONBREAK: Jailbreaking LLMs with Targeted Bit-flips

**Authors:** Researchers from CMU, UIUC, Stanford

**ArXiv:** arXiv:2412.07192 (2024)

**Summary:** Exposes new vulnerability to Rowhammer-based hardware fault injection attacks. Achieves 80-98% attack success rates on 10 open-source LLMs with only 5-25 bit-flips. Demonstrates end-to-end exploit on real GPU systems with 69-91% ASR.

---

### 5. GCG (Greedy Coordinate Gradient) Attack

**Authors:** Andy Zou, Zifan Wang, J. Zico Kolter, Matt Fredrikson

**ArXiv:** arXiv:2307.15043 (2023)

**Summary:** Pioneering discrete token optimization algorithm that finds adversarial suffixes to jailbreak aligned LLMs. Established foundation for most optimization-based jailbreak attacks.

### 5.1 Faster-GCG

**Authors:** Xiao Li, Zhuhong Li, et al.

**ArXiv:** arXiv:2410.15362 (2024)

**Summary:** Efficient variant achieving 29% and 8% higher success rates than original GCG with only 1/10 computational cost.

### 5.2 I-GCG: Improved Techniques for Optimization-Based Jailbreaking

**Authors:** Xiaojun Jia, Tianyu Pang, et al.

**ArXiv:** arXiv:2405.21018 (2024) - ICLR 2025

**Summary:** Improved techniques achieving nearly 100% attack success rate. Enhanced initialization and optimization strategies.

### 5.3 AmpleGCG: Universal and Transferable Generative Model

**Authors:** Zeyi Liao, Huan Sun (OSU)

**ArXiv:** arXiv:2404.07921 (2024) - COLM 2024

**Summary:** Trains a generative model of adversarial suffixes universal to any harmful queries. Achieves near 100% ASR on Llama-2-7B-chat and Vicuna-7B, transfers to GPT-3.5 with 99% ASR.

### 5.4 AttnGCG: Attention Manipulation Enhancement

**Authors:** Zijun Wang, et al.

**ArXiv:** arXiv:2410.09040 (2024)

**Summary:** Manipulates model attention scores to facilitate jailbreaking. Shows consistent improvements over GCG baseline.

---

### 6. JailbreakRadar: Comprehensive Assessment

**Authors:** Junjie Chu, Yugeng Liu, Ziqing Yang, et al. (CISPA, University of Oxford)

**ArXiv:** arXiv:2402.05668 (2024)

**Summary:** Systematic taxonomy and assessment of jailbreak attacks. Found that in realistic black-box settings, even latest LLMs face significant jailbreak risks. Static policies and questions are insufficient.

---

### 7. Crescendo: Multi-Turn LLM Jailbreak Attack

**Authors:** Mark Russinovich (Microsoft)

**Publication:** USENIX Security 2025

**Reference:** https://github.com/Azure/PyRIT

**Summary:** Multi-turn conversation technique that gradually leads models to generate harmful content. Effective against both open-source (LLaMA-2 70B, LLaMA-3 70B) and closed-source (GPT-4, Claude-3, Gemini-Pro) models.

---

### 8. AUTOdan: Dynamically Generated Jailbreak Prompts

**Authors:** Xiaogeng Liu, Nan Xu, Muhao Chen, Chaowei Xiao

**Publication:** ICLR 2024

**Summary:** Generates stealthy, context-aware jailbreak prompts that bypass model safeguards without manual crafting.

---

### 9. PAIR: Prompt Automatic Iterative Refinement

**Authors:** Patrick Chao, et al.

**Reference:** arXiv:2310.08419 (2023)

**Summary:** Uses another LLM to iteratively refine jailbreak prompts. Achieves jailbreaking in twenty queries or less. Black-box approach requiring no model access.

---

### 10. JULI: Jailbreaking Using LLM Introspection

**Authors:** Jesson Wang, et al.

**ArXiv:** arXiv:2505.11790 (2025)

**Summary:** Novel attack leveraging token log probabilities to construct adversarial prompts. Works in both open-weight and API-only black-box scenarios.

---

### 11. AutoAdv: Automated Multi-Turn Jailbreaking

**Authors:** Aashray Reddy, et al.

**Reference:** OpenReview (Under Review)

**Summary:** Training-free framework for automated multi-turn adversarial prompting. Achieves up to 95% ASR on Llama-3.1-8B within 6 turns.

---

### 12. J2: Jailbreaking to Jailbreak

**Authors:** Jeremy Kritz, et al. (Scale AI)

**ArXiv:** arXiv:2502.09638 (2025)

**Summary:** Uses capable LLMs to red team other models. Demonstrates that refusal-trained models can be turned into effective jailbreakers against other models.

---

### 13. VERA: Variational Inference Framework

**Authors:** Various

**ArXiv:** arXiv:2506.22666 (2025)

**Summary:** Black-box jailbreak method using variational inference. Effective against both open-source and closed-source API-only models.

---

### 14. Adversarial Reasoning at Jailbreaking Time

**Authors:** Mahdi Sabbaghi, et al.

**ArXiv:** arXiv:2502.01633 (2025)

**Summary:** Frames jailbreaking as a reasoning problem. Uses adversarial reasoning to achieve SOTA attack success rates.

---

### 15. Don't Say No: Jailbreaking by Suppressing Refusal

**Authors:** Yukai Zhou, Jian Lou, et al.

**ArXiv:** arXiv:2404.16369 (2024)

**Summary:** Novel attack that suppresses the model's refusal capability, causing it to bypass safety guardrails.

---

### 16. Catastrophic Jailbreak of Open-Source LLMs

**Authors:** Yangsibo Huang, Samyak Gupta, Mengzhou Xia, Kai Li, Danqi Chen

**Publication:** ICLR 2024

**Summary:** Exploits generation process vulnerabilities in open-source LLMs leading to catastrophic jailbreaks.

---

### 17. h4rm3l: Dynamic Benchmark of Composable Jailbreak Attacks

**Authors:** Maksym Andriushchenko, et al.

**Reference:** arXiv:2408.04811

**Summary:** Benchmark for composable jailbreak attacks testing LLM safety with dynamic attack patterns.

---

### 18. ProEAT: Adversarial Training for Multimodal LLMs

**Authors:** Various

**ArXiv:** arXiv:2503.04833 (2025)

**Summary:** First adversarial training paradigm tailored to defend against jailbreak attacks in multimodal LLMs. Outperforms baselines by +34% across text and image modalities.

---

### 19. The Resurgence of GCG Attacks

**Authors:** Various

**ArXiv:** arXiv:2509.00391 (2025)

**Summary:** Systematic appraisal of GCG and T-GCG across open-source LLMs of varying scales (Qwen2.5-0.5B, LLaMA-3.2-1B, GPT-OSS-20B).

---

## Key Research Findings

1. **Universal Vulnerability**: Both open-source and closed-source LLMs remain susceptible to jailbreak attacks despite safety alignment.

2. **Transferability**: Attacks developed on open-source models often transfer to closed-source APIs with high success rates.

3. **Diverse Attack Vectors**:
   - Optimization-based (GCG, ADC, Fastlier variants)
   - Multi-turn conversational (Crescendo, AutoAdv)
   - Hardware-based (PRISONBREAK bit-flips)
   - LLM-generated (PAIR, AutoDAN, J2)

4. **Defenses Are Partial**: Existing defenses can mitigate but not eliminate jailbreak threats. Adversarial training (ProEAT) shows promise but still has limitations.

5. **Black-Box Effectiveness**: Realistic black-box attacks (no model access) maintain significant success rates against current models, even frontier systems.

6. **Automation Trend**: Moving from manual prompt engineering to fully automated attack generation.

---

## References

1. MLCommons AI Literacy Security Working Group. "AILuminate Security: Introducing v0.5 of the Jailbreak Benchmark." October 2025.

2. Chao, P., Debenedetti, E., Robey, A., Andriushchenko, M., et al. "JailbreakBench: An Open Robustness Benchmark for Jailbreaking Large Language Models." arXiv:2404.01318 (2024).

3. Liu, Q., et al. "Efficient LLM Jailbreak via Adaptive Dense-to-sparse Constrained Optimization." arXiv:2405.09113 (2024).

4. "PRISONBREAK: Jailbreaking Large Language Models with at Most Twenty-Five Targeted Bit-flips." arXiv:2412.07192 (2024).

5. Zou, A., Wang, Z., Kolter, J.Z., Fredrikson, M. "Universal and Transferable Adversarial Attacks on Aligned Language Models." arXiv:2307.15043 (2023).

6. Li, X., Li, Z., Li, Q., et al. "Faster-GCG: Efficient Discrete Optimization Jailbreak Attacks." arXiv:2410.15362 (2024).

7. Jia, X., Pang, T., Du, C., et al. "Improved Techniques for Optimization-Based Jailbreaking." arXiv:2405.21018 (2024).

8. Liao, Z., Sun, H. "AmpleGCG: Learning a Universal and Transferable Generative Model of Adversarial Suffixes." arXiv:2404.07921 (2024).

9. Chu, J., Liu, Y., Yang, Z., et al. "JailbreakRadar: Comprehensive Assessment of Jailbreak Attacks Against LLMs." arXiv:2402.05668 (2024).

10. Russinovich, M. "The Crescendo Multi-Turn LLM Jailbreak Attack." USENIX Security 2025.

11. Liu, X., Xu, N., Chen, M., Xiao, C. "AutoDAN: Generating Stealthy Jailbreak Prompts." ICLR 2024.

12. Chao, P., Robey, A., Dobriban, E., et al. "Jailbreaking Black Box Large Language Models in Twenty Queries." arXiv:2310.08419 (2023).

13. Wang, J., et al. "JULI: Jailbreaking Large Language Models by Self-Introspection." arXiv:2505.11790 (2025).

14. Reddy, A., et al. "AutoAdv: Automated Adversarial Prompting for Multi-Turn Jailbreaking." OpenReview, 2025.

15. Kritz, J., Robinson, V., Vacareanu, R., et al. "Jailbreaking to Jailbreak." arXiv:2502.09638 (2025).

16. Zhou, Y., Lou, J., Huang, Z., et al. "Don't Say No: Jailbreaking LLM by Suppressing Refusal." arXiv:2404.16369 (2024).

17. Huang, Y., Gupta, S., Xia, M., et al. "Catastrophic Jailbreak of Open-source LLMs via Exploiting Generation." ICLR 2024.

18. Andriushchenko, M., et al. "h4rm3l: A Dynamic Benchmark of Composable Jailbreak Attacks." arXiv:2408.04811 (2024).

19. "Adversarial Training for Multimodal Large Language Models against Jailbreak Attacks." arXiv:2503.04833 (2025).

20. "The Resurgence of GCG Adversarial Attacks on Large Language Models." arXiv:2509.00391 (2025).