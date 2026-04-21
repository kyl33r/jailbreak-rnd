# Adversarial Reasoning at Jailbreaking Time

## Metadata

- **Title:** Adversarial Reasoning at Jailbreaking Time
- **Authors:** Mahdi Sabbaghi, Paul Kassianik, George Pappas, Yaron Singer, Amin Karbasi, Hamed Hassani
- **ArXiv:** arXiv:2502.01633
- **Date:** February 2025
- **Type:** Attack Paper (Reasoning)

## Summary

Frames jailbreaking as a reasoning problem using test-time compute to achieve SOTA attack success rates. Applies adversarial reasoning approach to automatic jailbreaking.

## Key Insights

1. **Reasoning Framework**: Treats jailbreaking as a reasoning task.

2. **Test-Time Compute**: Uses reasoning to guide attack generation.

3. **SOTA Results**: Achieves state-of-the-art ASR across multiple models.

4. **Loss-Guided**: Uses loss signal to guide test-time compute.

## Research Approach

### Adversarial Reasoning

1. **Problem Formulation**: Frame jailbreak as reasoning
2. **Loss Signal**: Use feedback to guide search
3. **Test-Time Compute**: Apply reasoning at inference time
4. **Iterate**: Refine through reasoning

## Key Innovation

Applies reasoning advances to jailbreaking:
- Chain-of-thought style reasoning
- Loss-guided search
- Test-time computation

## Results

- SOTA attack success rates
- Works across various models
- Effective black-box

## Transferability

Findings transfer to real-world scenarios:
- Works on API models
- Textual model attacks apply to practical settings

## Implications

- Reasoning capabilities can be exploited for attacks
- Test-time compute is crucial
- Need to consider reasoning attacks

## Key Finding

Reasoning-based approaches significantly improve jailbreak effectiveness, leveraging the reasoning capabilities of modern LLMs against themselves.