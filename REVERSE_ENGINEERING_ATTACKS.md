# Reverse Engineering Attacks on Open Source Models

Understanding how attackers bypass safety layers in open source models:

## Attack Vectors

### 1. Weight Manipulation (Most Direct)

| Attack | Method | Impact |
|--------|--------|--------|
| **Bit-flip attacks** | Flip model weights to corrupt safety neurons | Complete bypass |
| **Weight patching** | Direct modification of safety-related weights | Disable guardrails |

Reference: PRISONBREAK (arXiv:2412.07192) - achieves 80-98% ASR with 5-25 bit flips

### 2. Fine-Tuning Override

Attackers take a safety-aligned model and fine-tune on harmful data to override alignment:
- Use harmful instruction datasets
- Continuation training on refused queries
- Results in model ignoring safety warnings

### 3. Gradient-Based Jailbreaking (GCG Family)

Finds adversarial suffixes that trigger harmful generation:
- **Requires:** Model gradient access (white-box)
- **Method:** Optimize token suffix to minimize refusal loss
- **Tools:** GCG, I-GCG, Faster-GCG implementations available

### 4. Generation Process Exploitation

Exploits how the model generates text:
- Input manipulation during generation
- Output feedback loops
- Token-level manipulation

---

## Known Implementations

### Open Source Tools

| Tool | Repository | Purpose |
|------|-----------|---------|
| **GCG** | github.com/llm-attacks/llm-attacks | Original implementation |
| **I-GCG** | github.com/jiaxiaojunQAQ/I-GCG | Improved optimization |
| **AmpleGCG** | github.com/OSU-NLP-Group/AmpleGCG | Generative approach |
| **JailbreakBench** | github.com/jailbreakbench/jailbreakbench | Evaluation suite |
| **PyRIT** | github.com/Azure/PyRIT | Microsoft's red teaming tool |

### Bit-Flip / Weight Attacks

- PRISONBREAK research code (academic)
- Custom implementations possible with model weight access

---

## Defensive Mitigations

| Layer | Defense |
|-------|---------|
| **Model** | Adversarial training (ProEAT), diverse safety fine-tuning |
| **Input** | Input filtering, prompt sanitization |
| **Output** | Output classifiers (Llama Guard) |
| **Hardware** | Secure hardware for deployment |

## Key Risk Factor

**Open source models are vulnerable because:**
1. Weights are accessible → direct manipulation possible
2. Gradients available → optimization attacks work
3. Architecture visible → targeted exploits

For production, consider:
- Weight encryption at rest
- API-only access (don't expose model internals)
- Monitoring for adversarial patterns