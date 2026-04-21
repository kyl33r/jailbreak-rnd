# VERA: Variational Inference Framework

## Metadata

- **Title:** VERA: Variational Inference Framework for Jailbreaking Large Language Models
- **Authors:** Various
- **ArXiv:** arXiv:2506.22666
- **Date:** June 2025
- **Type:** Attack Paper (Variational)
- **Venue:** NeurIPS 2025

## Summary

Introduces a variational inference framework for automated black-box jailbreak attacks. Targets API-only models where only output tokens are available.

## Key Insights

1. **Black-Box Focus**: Designed for API-only models with no internal access.

2. **Variational Approach**: Uses variational inference for prompt generation.

3. **API Compatibility**: Works when only output tokens available.

4. **Dual Environment**: Effective on both open-source and closed-source APIs.

## Research Approach

### Variational Inference

1. **Latent Space**: Model attack prompts in latent space
2. **Variational Generation**: Sample from learned distribution
3. **Black-Box Optimization**: No gradients needed

## Models Tested

### Open-Source
- Llama2-7B
- Llama2-13B
- Vicuna-7B
- Baichuan2-7B
- Orca2-7B
- R2D2

### Closed-Source
- GPT-3.5
- Gemini-Pro

## Key Innovation

- Frameworks jailbreaking as variational inference
- No gradient access required
- Works on API-only models

## Results

- Best performance among black-box approaches
- Consistent across model types
- Achieves high ASR

## Implications

- API-only access still vulnerable
- Black-box attacks increasingly sophisticated
- Need for API-level defenses