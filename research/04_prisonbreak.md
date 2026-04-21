# PRISONBREAK: Jailbreaking LLMs with Targeted Bit-flips

## Metadata

- **Title:** PRISONBREAK: Jailbreaking Large Language Models With at Most Twenty-Five Targeted Bit-flips
- **Authors:** Researchers from CMU, UIUC, Stanford, and others
- **ArXiv:** arXiv:2412.07192
- **Date:** December 2024
- **Type:** Hardware Attack Paper

## Summary

Exposes a new vulnerability in commercial-scale safety-aligned LLMs to hardware-based fault injection attacks. The PRISONBREAK attack achieves high jailbreak success rates through targeted bit-flips, requiring no adversarial prompts or API access.

## Key Insights

1. **Hardware Vulnerability**: First demonstration of Rowhammer-based fault injection reliably jailbreaking models on real GPU hardware.

2. **Massive Attack Success Rates**:
   - 80-98% ASR on 10 open-source LLMs with only 5-25 bit-flips
   - 69-91% ASR in end-to-end GPU attack (GDDR6)

3. **No Prompt Engineering**: Unlike traditional attacks, requires no adversarial suffix crafting or multi-turn conversations.

4. **Model Weights Manipulation**: Exploits bit-level vulnerabilities in model weight representations.

5. **Real-World Exploit**: Complete end-to-end attack demonstrated on actual GPU systems.

## Attack Methodology

- **Targeted Bit-Search**: Hardware-aware search for vulnerable bit positions
- **Rowhammer Exploitation**: Leveraging physical memory fault injection
- **Minimal Bit-Flips**: Only 5-25 bit modifications needed

## Models Tested

10 open-source language models evaluated:
- Multiple Llama variants
- Various Mistral-based models
- Qwen models
- And others

## Key Finding

LLMs are vulnerable not just to prompt-based attacks but also to physical hardware-level manipulations that bypass all software guardrails entirely.

## Implications

- Hardware security is crucial for AI safety
- Traditional software defenses insufficient against physical attacks
- Need for hardware-software co-design in secure AI deployment