# ProEAT: Adversarial Training for Multimodal LLMs

## Metadata

- **Title:** Adversarial Training for Multimodal Large Language Models against Jailbreak Attacks
- **Authors:** Various
- **ArXiv:** arXiv:2503.04833
- **Date:** March 2025
- **Type:** Defense Paper

## Summary

First adversarial training paradigm specifically designed to defend against jailbreak attacks in multimodal LLMs. Outperforms baselines by +34% across text and image modalities.

## Key Insights

1. **Multimodal Defense**: First adversarial training for multimodal LLM safety.

2. **High Defense Rate**: +34% improvement over baselines.

3. **Low Cost**: Only 1% reduction in clean accuracy.

4. **Dual Modality**: Works on both text and image inputs.

## Research Approach

### Defense Methodology

1. **Adversarial Training**: Incorporate adversarial examples in training
2. **Multimodal Focus**: Both text and image attacks
3. **Robustness**: Build resistance to jailbreaks

## Results

| Metric | Improvement |
|--------|-------------|
| Text Modality | +34% |
| Image Modality | +34% |
| Clean Accuracy | -1% |

## Key Innovation

- Extends traditional AT to multimodal
- Composable defense across modalities
- Practical real-world applicability

## Limitations

- Still has some vulnerabilities
- Some utility trade-off
- Not complete solution

## Implications

- Defense possible but challenging
- Multimodal safety needs attention
- Trade-off between safety and utility

## Key Finding

Adversarial training provides a viable defense direction but cannot fully eliminate jailbreak vulnerabilities.