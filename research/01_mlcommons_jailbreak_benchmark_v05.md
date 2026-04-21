# MLCommons Jailbreak Benchmark v0.5

## Metadata

- **Title:** AILuminate Security: Introducing v0.5 of the Jailbreak Benchmark
- **Authors:** MLCommons AI Literacy Security Working Group
- **Date:** October 15, 2025
- **Type:** Benchmark Paper
- **URL:** https://mlcommons.org/ailuminate/jailbreak-v0.5-whitepaper/

## Summary

This paper presents v0.5 of the MLCommons Jailbreak benchmark, which evaluates text-to-text (T2T) LLMs and text+image-to-text (T+I2T) VLMs against various jailbreak tactics in realistic black-box settings.

## Key Insights

1. **Comprehensive Evaluation Framework**: Tests systems against diverse jailbreak tactics combining policies from multiple AI companies (OpenAI, Anthropic, Google, Meta).

2. **Real-World Black-Box Testing**: Focuses on realistic attack scenarios where attackers have no internal model access.

3. **Frontier Model Vulnerability**: Demonstrates that jailbreaks are still discovered at alarming rates even for frontier models from major AI companies.

4. **Rapid Mitigation Paradox**: While frontier model companies may quickly mitigate discovered jailbreaks, new vulnerabilities continuously emerge.

5. **Open-Source Focus**: Results are limited to open-source models, though findings are expected to generalize to other architectures.

## Research Contributions

- Benchmark with deidentified SUTs (Systems Under Test) and tactics
- Monitoring framework using Plan-Do-Check-Act (PDCA) cycle
- 2025 snapshot of jailbreak resistance across multiple model families

## Vulnerabilities Addressed

- Various "jailbreak" techniques used by adversarial actors to bypass LLM and VLM guardrails
- Methods causing models to produce harmful or undesired output

## Limitations

- Results limited to open-source models tested
- SUTs and tactics are deidentified for security reasons