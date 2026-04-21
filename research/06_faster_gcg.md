# Faster-GCG: Efficient Discrete Optimization Jailbreak Attacks

## Metadata

- **Title:** Faster-GCG: Efficient Discrete Optimization Jailbreak Attacks against Aligned Large Language Models
- **Authors:** Xiao Li, Zhuhong Li, Qiongxiu Li, Bingze Lee, Jinghao Cui, Xiaolin Hu
- **ArXiv:** arXiv:2410.15362
- **Date:** October 2024
- **Type:** Attack Paper (Optimization)

## Summary

An efficient variant of the GCG attack that achieves significantly higher attack success rates with only 1/10 of the computational cost by optimizing the discrete token optimization process.

## Key Insights

1. **Computational Efficiency**: Achieves 29% higher success rate on Llama2-7B-chat and 8% higher on Vicuna-13B-v1.5 compared to original GCG.

2. **Cost Reduction**: Only requires 1/10 of original GCG's computational resources.

3. **Improved Transferability**: Exhibits enhanced transferability when testing on closed-source LLMs like ChatGPT.

4. **Deep Optimization**: Analyzes and improves the design of GCG at a fundamental level.

## Research Approach

- **Token-Level Improvement**: More efficient token selection strategy
- **Gradient Utilization**: Better use of gradient information
- **Updated Rules**: Optimized coordinate selection rules

## Results

| Model | GCG ASR | Faster-GCG ASR | Improvement |
|-------|---------|--------------|------------|
| Llama2-7B-chat | Baseline | +29% | Significant |
| Vicuna-13B-v1.5 | Baseline | +8% | Moderate |

## Key Techniques

1. **Improved Token Scoring**: More effective scoring mechanism for candidate tokens
2. **Efficient Coordinate Selection**: Better positions to update
3. **Optimized Search Strategy**: Faster convergence

## Code Available

- Part of open-source optimization-based jailbreak research

## Significance

Demonstrates that the original GCG was suboptimal and there is significant room for improvement in optimization-based jailbreaking approaches.