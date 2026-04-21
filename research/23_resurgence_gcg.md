# The Resurgence of GCG Attacks

## Metadata

- **Title:** The Resurgence of GCG Adversarial Attacks on Large Language Models
- **Authors:** Various
- **ArXiv:** arXiv:2509.00391
- **Date:** August 2025
- **Type:** Attack Paper (Survey/Empirical)

## Summary

Systematic appraisal of GCG and T-GCG attacks across open-source LLMs of varying scales. Evaluates attack effectiveness on models at different sizes.

## Key Insights

1. **Scale Analysis**: Tests across various model scales.

2. **Modern Models**: Uses Qwen2.5-0.5B, LLaMA-3.2-1B, GPT-OSS-20B.

3. **Revised Assessment**: Re-evaluates GCG effectiveness on newer models.

4. **Emerging Patterns**: Identifies patterns across model sizes.

## Research Approach

### Evaluation

1. **Model Selection**: Diverse model scales
2. **Attack Testing**: GCG and T-GCG variants
3. **Dataset**: AdvBench and other harmful behaviors
4. **Analysis**: Pattern identification

## Models Evaluated

- Qwen2.5-0.5B (small)
- LLaMA-3.2-1B (medium)
- GPT-OSS-20B (large)

## Findings

- GCG remains effective across scales
- Larger models more resistant but not immune
- T-GCG shows improvements in some cases

## Implications

- Attack effectiveness scales with model size
- Larger models not immune
- Defense requires more than scale

## Key Finding

GCG-style attacks remain relevant and effective even against newer, larger models, demonstrating persistent vulnerabilities.