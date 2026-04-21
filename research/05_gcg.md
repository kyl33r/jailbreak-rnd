# GCG: Greedy Coordinate Gradient Attack

## Metadata

- **Title:** Universal and Transferable Adversarial Attacks on Aligned Language Models
- **Authors:** Andy Zou, Zifan Wang, J. Zico Kolter, Matt Fredrikson
- **ArXiv:** arXiv:2307.15043
- **Date:** July 2023
- **Type:** Attack Paper (Foundational)
- **Venue:** NeurIPS 2023

## Summary

The pioneering work that established gradient-based adversarial prompting for LLM jailbreaking. GCG treats jailbreak as a discrete token optimization problem and finds adversarial suffixes that bypass safety alignments.

## Key Insights

1. **Foundational Work**: First major gradient-based approach to adversarial jailbreaking that established the field.

2. **Discrete Optimization**: Models jailbreak as finding a suffix string that when appended to a harmful query triggers the model to comply.

3. **Transferability**: Adversarial suffixes often transfer across different models and query types.

4. **Token-Level Attack**: Operates at the token level, modifying discrete token sequences.

5. **Black-Box Adaptation**: Later adapted for black-box scenarios where gradient access is unavailable.

## Research Approach

- **Loss Optimization**: Maximize probability of generating harmful continuation
- **Greedy Coordinate Descent**: Iterate through token positions, selecting best replacements
- **Adversarial Suffix**: Find string that tricks model into compliance

## Technical Innovation

```
For each token position:
  1. Compute gradients with respect to the embedding
  2. Score candidate tokens by gradient × embedding
  3. Greedily select best token
  4. Update suffix iteratively
```

## Dataset: AdvBench

- Comprehensive collection of harmful behaviors
- Used by subsequent jailbreak research
- Foundation for jailbreak evaluation

## Impact

GCG established the foundation for most subsequent optimization-based jailbreak attacks, including:
- Faster-GCG
- I-GCG
- AmpleGCG
- ADC
- And many variants

## Limitations

- Requires gradient access (white-box)
- Computationally expensive
- Suffix length limited

## Legacy

Gave rise to entire family of GCG-based attacks and inspired research into:
- Transferable attacks
- Black-box variants
- Efficiency improvements
- Multimodal extensions