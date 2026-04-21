# AutoAdv: Automated Multi-Turn Jailbreaking

## Metadata

- **Title:** AutoAdv: Automated Adversarial Prompting for Multi-Turn Jailbreaking of Large Language Models
- **Authors:** Aashray Reddy, et al.
- **Date:** 2025
- **Type:** Attack Paper (Multi-Turn)
- **Venue:** Under Review (OpenReview)

## Summary

Training-free framework for automated multi-turn adversarial prompting. Achieves up to 95% ASR on Llama-3.1-8B across 6 turns.

## Key Insights

1. **Multi-Turn Effectiveness**: Up to 95% ASR on Llama-3.1-8B within 6 turns.

2. **Improvement Over Single-Turn**: Multi-turn interactions improve ASR by up to 24% vs single-turn.

3. **Training-Free**: No training required, uses existing models.

4. **Broad Coverage**: Works on commercial and open-source models.

## Research Approach

### Framework

1. **Disguise**: Masks harmful requests as benign initially
2. **Iterate**: Gradually reveals true intent
3. **Refine**: Uses feedback to improve attacks

## Tested Models

- GPT-4o-mini (closed)
- Qwen3-235B (open)
- Mistral-7B (open)
- Llama-3.1-8B (open)

## Results

| Model | Single-Turn ASR | Multi-Turn ASR | Improvement |
|-------|-----------------|----------------|-------------|
| Llama-3.1-8B | ~71% | 95% | +24% |

## Key Innovation

- Automated persona modulation
- Gradual intent revelation
- Iterative refinement

## Advantages

- **Scalable**: No manual crafting
- **Effective**: High success rates
- **Versatile**: Works across models

## Code

Available through referenced repositories

## Key Finding

Multi-turn conversations significantly increase attack success by gradually building trust/escalation.