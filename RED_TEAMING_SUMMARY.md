# Red Teaming Summary: Effective Jailbreak Methods

For red team evaluations, ranked by reliability and practicality:

## Top Approaches for Open Source Models

### 1. Optimization-Based (Highest Success)

| Method | ASR | Access Required | Notes |
|--------|-----|--------------|-------|
| **I-GCG** | ~100% | White-box | Best success rate, open-source code available |
| **AmpleGCG** | ~100% | White-box train, black-box deploy | Universal, transfers to APIs |
| **ADC** | 96%+ | White-box | Efficient, good for批量 testing |
| **Faster-GCG** | +29% over GCG | White-box | 10x faster |

### 2. LLM-Generated (Best for API/Black-box)

| Method | ASR | Access Required | Notes |
|--------|-----|--------------|-------|
| **PAIR** | High | Black-box | <20 queries typical |
| **AutoDAN** | High | Black-box | Automated generation |
| **Crescendo** | High | Conversational API | Multi-turn, effective |

### 3. Black-Box Only (For Closed APIs)

| Method | Notes |
|--------|-------|
| **JULI** | Works with log probability APIs |
| **VERA** | Variational inference approach |
| **Adversarial Reasoning** | Reasoning-guided search |

## Recommended Red Teaming Workflow

1. **Start with open-source**: Test on Llama, Mistral, Vicuna with I-GCG/AmpleGCG
2. **Transfer testing**: Use trained suffixes on closed APIs
3. **Multi-turn escalation**: Test conversational defenses with Crescendo/AutoAdv
4. **Evaluate defenses**: Compare against JailbreakBench/Llama Guard

## Key Resources

- JailbreakBench: https://jailbreakbench.github.io/
- PyRIT (Microsoft): https://github.com/Azure/PyRIT
- AdvBench dataset: From GCG paper

## For Closed-Source/Production

PAIR, Crescendo, and AutoAdv are most practical as they require only API access and no internal model knowledge.