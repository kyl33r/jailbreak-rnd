# JailbreakBench: An Open Robustness Benchmark for Jailbreaking LLMs

## Metadata

- **Title:** JailbreakBench: An Open Robustness Benchmark for Jailbreaking Large Language Models
- **Authors:** Patrick Chao, Edoardo Debenedetti, Alexander Robey, Maksym Andriushchenko, Francesco Croce, Viral Sehwag, Edgar Dobriban, Nicolas Flammarion, George J. Pappas, Florian Tramer, Hamed Hassani, Eric Wong
- **ArXiv:** arXiv:2404.01318
- **Date:** April 2024
- **Type:** Benchmark Paper
- **URL:** https://github.com/jailbreakbench/jailbreakbench

## Summary

JailbreakBench is an open-sourced benchmark designed to evaluate LLM robustness against jailbreak attacks. It provides an evolving repository of state-of-the-art jailbreak prompts, evaluation code, and a leaderboard.

## Key Insights

1. **Open-Source Infrastructure**: Addresses the reproducibility problem in jailbreak research by providing open access to jailbreak prompts corresponding to attacked and defended models.

2. **Evaluation Framework**: Includes carefully designed humaneval prompts, model-evaluated prompts, and an evolving dataset of jailbreak prompts.

3. **Llama Guard Effectiveness**: Identifies Llama Guard (Inan et al., 2023) as a preferable jailbreaking evaluator for safety assessment.

4. **Persistent Susceptibility**: Both open-source and closed-source LLMs remain susceptible to jailbreaking attacks that can be mitigated but not eliminated by existing defenses.

5. **Benchmark Components**:
   - Evolving repository of SOTA jailbreak prompts
   - Evaluation code
   - Leaderboard (https://jailbreakbench.github.io/)

## Research Methodology

- **Attack Collection**: Curated set of jailbreak attack methods
- **Defense Evaluation**: Assessment of current defense techniques
- **Behavioral Dataset**: 18% of behaviors from AdvBench (Zou et al., 2023)
- **Continuous Updates**: Evolving benchmark since February 2024

## Key Findings

- Defense mechanisms exist but are insufficient
- New jailbreak attacks continue to be discovered
- No single defense provides complete protection

## Dataset Availability

- Jailbreak prompts available at Zenodo: https://zenodo.org/records/10714577