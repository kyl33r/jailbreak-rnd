# Jailbreak Research - Attack Implementations

This directory contains attack implementations for defensive security research.

## Setup

### Quick Start: Black-Box Testing

```bash
# Test with known adversarial patterns
python test_adversarial.py --model qwen3:8b --output results.json
```

### Full GCG Attacks

For white-box GCG attacks (requires model weights with gradient access):

```bash
# I-GCG - most effective
cd i_gcg
pip install -r requirements.txt
python attack_llm_core_best_update_ours_target.py --model_path /path/to/model
```

## Directory Structure

```
attack_implementations/
├── test_adversarial.py    # Black-box pattern testing (works with Ollama)
├── gcg/               # Original GCG
├── i_gcg/             # Improved GCG (ICLR 2025)
├── amplegcg/          # Universal suffixes
├── image_jailbreak/    # Image generation attacks
└── coljailbreak/      # Collaborative image attacks
```

## Requirements

- Python 3.9+
- CUDA GPU (for white-box attacks)
- Model weights (see individual READMEs)

## Models

White-box attacks need local model weights. Options:
- Llama-2-7b-chat (Meta)
- Vicuna-7b-v1.5 (LMSYS)
- Convert Ollama model to GGUF