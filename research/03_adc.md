# ADC: Adaptive Dense-to-sparse Constrained Optimization

## Metadata

- **Title:** Efficient LLM Jailbreak via Adaptive Dense-to-sparse Constrained Optimization
- **Authors:** Qi Liu, Matt Fredrikson et al.
- **ArXiv:** arXiv:2405.09113
- **Date:** May 2024 (NeurIPS 2024)
- **Type:** Attack Paper
- **Venue:** NeurIPS 2024

## Summary

Introduces a novel token-level attack method called Adaptive Dense-to-sparse Constrained Optimization (ADC) that successfully jailbreaks multiple open-source LLMs through discrete token optimization.

## Key Insights

1. **Token-Level Optimization**: Draws inspiration from the difficulties of discrete token optimization, treating jailbreak as a constrained optimization problem.

2. **High Attack Success Rates**:
   - 96.2% ASR on Llama2-chat-7B
   - 26.5% ASR on adversarially trained LLM Zephyr-R2D2
   - Significant improvements over other token-level jailbreak methods

3. **Efficiency Gains**: Combines dense-to-sparse optimization strategies for faster computation.

4. **Open-Source Vulnerability**: Successfully breaches several open-source large language models:
   - Llama2-chat-7B
   - Vicuna-v1.5-7B
   - Zephyr-7b-β
   - Zephyr 7B R2D2 (adversarially trained)

## Research Approach

- **Problem Formulation**: Discrete token optimization with constraints
- **Method**: Adaptive dense-to-sparse constrained optimization
- **Evaluation**: Tested on 7 open-source LLMs

## Technical Details

| Model | GCG Time (min) | ADC Time (min) | Improvement |
|-------|---------------|---------------|------------|
| Llama2-chat-7B | 53.8 | 0.93× | +42.4% ASR |

- Early stop rate significantly reduced
- Near 100% attack effectiveness achieved

## Code Available

- https://github.com/hukkai/adc_llm_attack

## Key Finding

Even adversarially trained models (Zephyr-R2D2) designed specifically to defend against attacks remain vulnerable to optimization-based jailbreaks.