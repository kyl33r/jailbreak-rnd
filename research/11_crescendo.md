# Crescendo: Multi-Turn LLM Jailbreak Attack

## Metadata

- **Title:** The Crescendo Multi-Turn LLM Jailbreak Attack
- **Authors:** Mark Russinovich
- **Publication:** USENIX Security 2025
- **Date:** January 2025
- **Type:** Attack Paper (Conversation-based)
- **Venue:** USENIX Security Symposium

## Summary

Introduces a multi-turn conversation attack that gradually leads LLMs to generate harmful content through escalating conversation patterns. Effective against both open-source and closed-source models.

## Key Insights

1. **Gradual Escalation**: Uses multi-turn conversations to gradually bypass safety guardrails.

2. **Broad Effectiveness**: Works against:
   - Open-source: LLaMA-2 70B, LLaMA-3 70B
   - Closed-source: GPT-3.5 Turbo, GPT-4, Claude-2, Claude-3, Gemini-Pro

3. **No Special Access**: Requires only conversational API access.

4. **Automated Variant**: CrescendoAutomation available for scalable attacks.

## Research Approach

### Attack Methodology

1. **Initial Context**: Start with seemingly benign framing
2. **Gradual Build**: Step-by-step escalation toward harmful goal
3. **Context Exploitation**: Leverage accumulated context for compliance

### Automation

- Available through PyRIT (Python Risk Identification Tool)
- Automated escalation strategies
- Scalable to large numbers of targets

## Code Available

- https://github.com/Azure/PyRIT
- Complete conversation datasets at referenced repositories

## Defenses Challenged

- Refusal training
- Contextual guardrails
- Output filtering

## Key Finding

Single-turn attacks are insufficient; multi-turn conversations can gradually erode model resistance through accumulated context.

## Implications

- Conversation-based attacks are a significant threat vector
- Model behavior changes across conversation length
- Need for conversation-level safety evaluation