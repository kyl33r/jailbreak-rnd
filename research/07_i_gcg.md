# I-GCG: Improved Techniques for Optimization-Based Jailbreaking

## Metadata

- **Title:** Improved Techniques for Optimization-Based Jailbreaking on Large Language Models
- **Authors:** Xiaojun Jia, Tianyu Pang, Chao Du, Yihao Huang, Jindong Gu, Yang Liu, Xiaochun Cao, Min Lin
- **ArXiv:** arXiv:2405.21018
- **Date:** May 2024
- **Type:** Attack Paper (Optimization)
- **Venue:** ICLR 2025

## Summary

Presents several improved empirical techniques for optimization-based jailbreaks like GCG, achieving nearly 100% attack success rate through enhanced initialization and optimization strategies.

## Key Insights

1. **Near-Perfect Success**: Achieves nearly 100% attack success rate through improved techniques.

2. **Comprehensive Improvements**: Multiple empirical techniques that enhance GCG-style attacks.

3. **Better Initialization**: More effective initialization strategies for adversarial suffixes.

4. **Optimized Updates**: More efficient token replacement and update rules.

## Research Approach

### Key Techniques Developed

1. **Enhanced Initialization**:
   - Improved starting token sequences
   - Better initial suffix selection

2. **Optimized Scoring**:
   - More effective token scoring mechanisms
   - Better gradient utilization

3. **Refined Coordinate Selection**:
   - More intelligent position selection
   - Adaptive iteration strategies

## Results

- Near 100% attack success rate achieved
- Significantly outperforms previous SOTA methods
- Works across multiple open-source models

## Code Available

- https://github.com/jiaxiaojunQAQ/I-GCG

## Citation

```bibtex
@article{jia2024improved,
  title={Improved Techniques for Optimization-Based Jailbreaking on Large Language Models},
  author={Xiaojun Jia and Tianyu Pang and Chao Du and Yihao Huang and Jindong Gu and Yang Liu and Xiaochun Cao and Min Lin},
  year={2024},
  eprint={2405.21018}
}
```

## Key Finding

The original GCG had significant room for empirical improvements that can nearly double the attack success rate through better initialization and optimization strategies.