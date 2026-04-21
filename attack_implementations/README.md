# Attack Implementations for Research

This directory contains implementations of jailbreak attack methods for defensive security research.

## Directory Structure

```
attack_implementations/
├── gcg/              # Original GCG attack
├── i_gcg/            # Improved GCG (I-GCG)
├── amplegcg/          # AmpleGCG - Generative approach
├── image_jailbreak/   # Chain-of-Jailbreak for images
└── coljailbreak/      # ColJailBreak for images
```

## Attack Methods Overview

### Text LLM Attacks

| Directory | Method | Description |
|-----------|--------|-------------|
| `gcg/` | GCG | Original Greedy Coordinate Gradient attack |
| `i_gcg/` | I-GCG | Improved techniques, ~100% ASR |
| `amplegcg/` | AmpleGCG | Universal transferable suffixes |

### Image Generation Attacks

| Directory | Method | Description |
|-----------|--------|-------------|
| `image_jailbreak/` | Chain-of-Jailbreak | Multi-step editing attack |
| `coljailbreak/` | ColJailBreak | Collaborative generation/editing |

## Usage

Each implementation has its own README and requirements. See individual directories for details.

**Important:** These tools are for authorized security research only.

## Requirements

- Python environment with GPU support
- Model weights (Llama-2, Vicuna, or target models)
- See each implementation's requirements.txt

## References

- GCG: arXiv:2307.15043
- I-GCG: arXiv:2405.21018 (ICLR 2025)
- AmpleGCG: arXiv:2404.07921 (COLM 2024)
- CoJ: arXiv:2410.03869 (ACL 2025)
- ColJailBreak: Ma & Zhang, 2024