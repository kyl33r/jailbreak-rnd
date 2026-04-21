# Don't Say No: Jailbreaking by Suppressing Refusal

## Metadata

- **Title:** Don't Say No: Jailbreaking LLM by Suppressing Refusal
- **Authors:** Yukai Zhou, Jian Lou, Zhijie Huang, Zhan Qin, Yibei Yang, Wenjie Wang
- **ArXiv:** arXiv:2404.16369
- **Date:** April 2024
- **Type:** Attack Paper (Refusal Suppression)

## Summary

Novel attack that suppresses the model's refusal capability, causing it to bypass safety guardrails by disabling its refusal mechanism.

## Key Insights

1. **Refusal Suppression**: Attacks model's ability to refuse, not just bypass filters.

2. **Mechanism Attack**: Targets refusal mechanism itself.

3. **Effective Bypass**: Successfully bypasses safety guardrails.

4. **Novel Vector**: Different approach from prompt injection.

## Research Approach

### Attack Methodology

1. **Identify Refusal Mechanism**: Find what enables refusal
2. **Suppress Capability**: Attack refusal system
3. **Bypass**: With refusal disabled, bypass safety

## Key Innovation

Instead of hiding harmful intent, attacks the model's refusal mechanism directly:
- Targets safety systems
- Disables refusal capability
- Forces compliance

## Results

- Successful jailbreak across models
- Bypasses standard defenses
- Novel attack vector

## Implications

- Refusal is a vulnerability
- Safety depends on single mechanism
- Need redundant safety systems

## Key Finding

Model safety depends on refusal capability; disabling this mechanism makes jailbreaking trivial.