# JULI: Jailbreaking Using LLM Introspection

## Metadata

- **Title:** JULI: Jailbreak Large Language Models by Self-Introspection
- **Authors:** Jesson Wang, et al.
- **ArXiv:** arXiv:2505.11790
- **Date:** May 2025
- **Type:** Attack Paper (Introspection)

## Summary

Novel attack that leverages token log probabilities to construct adversarial prompts. Works in both open-weight and API-only scenarios where log probs are available.

## Key Insights

1. **Log Probability Exploitation**: Uses token-level log probabilities for attack generation.

2. **API Compatibility**: Works on API-only models that return token log probs.

3. **Black-Box Effective**: No gradient access needed.

4. **Dual Scenarios**: Works on both open-weight and API models.

## Research Approach

### Methodology

1. **Introspection**: Analyze token log probabilities
2. **Pattern Discovery**: Find tokens correlated with compliance
3. **Suffix Construction**: Build adversarial prompt based on patterns
4. **Attack**: Deploy crafted prompt

## Key Innovation

Exploits log probability information available through APIs:
- DeepSeek API returns token log probs
- OpenAI and others offer top-k probabilities
- Enables white-box-style attacks on black-box APIs

## Scenarios

### Open-Weight Models
- Full gradient/logit access
- Traditional optimization possible

### API-Only Models
- Limited to log probability access
- Can still achieve high ASR with JULI

## Results

- Works in black-box settings
- High ASR on various models
- Exploits standard API features

## Key Finding

Log probability APIs, intended for helpful features, enable new attack vectors that bypass traditional black-box assumptions.

## Implications

- API features can be security vulnerabilities
- Need to reconsider API access models
- Log probabilities enable sophisticated attacks