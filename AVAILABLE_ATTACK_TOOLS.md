# Pre-built Attack Models & Tools

From open source research, here aredeployable tools for red teaming:

## Pre-Trained Models (Direct Use)

| Model | Location | Purpose |
|-------|----------|---------|
| **AmpleGCG** | HuggingFace: osunlp/AmpleGCG-llama2-sourced-llama2-7b-chat | Generates jailbreak suffixes |
| **Llama Guard** | Meta (meta-llama/Llama-Guard-2-8B) | Safety evaluator |

## Ready-to-Use Implementations

### Optimization-Based

```
# GCG implementations
- https://github.com/llm-attacks/llm-attacks
- https://github.com/jiaxiaojunQAQ/I-GCG (ICLR 2025)
- https://github.com/hukkai/adc_llm_attack (ADC)

# Usage: Run optimization on target model
python attack.py --model vicuna-7b --target harmful_query
```

### Generative (AmpleGCG)

```
# Already trained, generates suffixes instantly
python generate_suffix.py --query "how to make bomb"
# Returns: adversarial suffix in seconds
```

## Attack Frameworks

| Framework | URL | Notes |
|-----------|-----|-------|
| **PyRIT** (Microsoft) | github.com/Azure/PyRIT | Automated red teaming |
| **JailbreakBench** | jailbreakbench.github.io | Evaluation + prompts |
| **AdvBench** | From GCG paper | Harmful behavior dataset |

## Pre-Generated Jailbreak Prompts

- `JailbreakBench` repository includes 1400+ curated jailbreak prompts
- Available at: https://zenodo.org/records/10714577
- Ready to test immediately

## Quick Start for Red Teaming

```python
# Option 1: Use pre-generated prompts from JailbreakBench
from jailbreakbench import get_prompts
prompts = get_prompts()

# Option 2: Use AmpleGCG to generate new
from amplegcg import generate
suffix = generate("harmful_request")

# Option 3: Use PyRIT automation
from pyrit import RedTeamer
rt = RedTeamer(target_model="gpt-4")
result = rt.jailbreak("your harmful query")
```

## Model-Specific Notes

| Model | Best Attack | ASR |
|-------|------------|-----|
| Llama-2 | I-GCG/AmpleGCG | ~100% |
| Llama-3 | AutoAdv (multi-turn) | 95% |
| Vicuna | GCG variants | High |
| Mistral | PAIR/AutoDAN | High |
| Qwen | GCG variants | High |

## For Testing Different Modalities

- **Code generation**: Standard prompts work
- **Image generation**: See multimodal jailbreak research
- **Text-to-image**: Different attack vectors (research emerging)