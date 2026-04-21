# AmpleGCG: Universal and Transferable Generative Model

## Metadata

- **Title:** AmpleGCG: Learning a Universal and Transferable Generative Model of Adversarial Suffixes for Jailbreaking Both Open and Closed LLMs
- **Authors:** Zeyi Liao, Huan Sun
- **ArXiv:** arXiv:2404.07921
- **Date:** April 2024
- **Type:** Attack Paper (Generative)
- **Venue:** COLM 2024

## Summary

Trains a generative model of adversarial suffixes that is universal to any harmful query and transferable from open-source to closed-source LLMs. Achieves near 100% ASR on open-source models and 99% on GPT-3.5.

## Key Insights

1. **Universal Generator**: Can generate hundreds of adversarial suffixes for any harmful query in seconds.

2. **High Transferability**: Suffixes trained on open-source models transfer to closed-source APIs with 99% ASR on GPT-3.5.

3. **Efficiency**: Generates complete attack prompts in only 4 seconds.

4. **Model-Agnostic**: Universal to different harmful queries, not specific to particular targets.

## Research Approach

### Training Methodology

1. **Suffix Generation Model**: Train a model to generate adversarial suffixes
2. **Universal Training**: Train once, apply to any query
3. **Transfer Learning**: Leverage open-source training for closed-source attacks

## Results

| Model | ASR |
|-------|-----|
| Llama-2-7B-chat | ~100% |
| Vicuna-7B | ~100% |
| GPT-3.5 (closed) | 99% |

## Key Innovation

Instead of finding individual suffixes through optimization, trains a generative model that learns the distribution of effective adversarial suffixes.

## Advantages

- **Speed**: Generates suffixes instantly vs. minutes/hours of optimization
- **Universal**: One model, any query
- **Transferable**: Open-source training transfers to closed APIs
- **Scalable**: Can generate new attacks on-demand

## Code Available

- https://github.com/OSU-NLP-Group/AmpleGCG
- Model: https://huggingface.co/osunlp/AmpleGCG-llama2-sourced-llama2-7b-chat

## Implications

Demonstrates that adversarial suffix patterns can be learned as a distribution and generalized across queries and models.