# AutoDAN: Dynamically Generated Jailbreak Prompts

## Metadata

- **Title:** AutoDAN: Generating Stealthy Jailbreak Prompts for Aligned Language Models
- **Authors:** Xiaogeng Liu, Nan Xu, Muhao Chen, Chaowei Xiao
- **Publication:** ICLR 2024
- **Date:** 2024
- **Type:** Attack Paper (LLM-Generated)
- **Venue:** ICLR 2024

## Summary

Introduces a method for automatically generating stealthy, context-aware jailbreak prompts that bypass model safeguards without manual prompt crafting. Uses an LLM to generate and refine attack prompts.

## Key Insights

1. **Automated Generation**: No manual prompt engineering required.

2. **Stealthy**: Generates contextually appropriate prompts that appear benign.

3. **Adaptive**: LLM-generated prompts adapt to target model.

4. **Transferable**: Works across different target models.

## Research Approach

### Generation Process

1. **Initial Prompt**: Generate seed jailbreak prompt
2. **Refinement**: LLM refines to bypass filters
3. **Iteration**: Progressive improvement

## Key Innovation

Uses an auxiliary LLM to:
- Generate initial jailbreak prompts
- Refine prompts based on target responses
- Iterate toward successful attacks

## Advantages

- **Human-Free**: No manual prompt crafting needed
- **Scalable**: Can generate unlimited prompts
- **Adaptive**: Works even with model updates
- **Stealthy**: Generates contextually natural language

## Similar Approaches

- PAIR (Prompt Automatic Iterative Refinement)
- J2 (Jailbreaking to Jailbreak)

## Code

Available through referenced GitHub repositories

## Implications

LLMs can be used to attack other LLMs, creating an adversarial ecosystem where AI systems attack each other.