# PAIR: Prompt Automatic Iterative Refinement

## Metadata

- **Title:** Jailbreaking Black Box Large Language Models in Twenty Queries
- **Authors:** Patrick Chao, Alexander Robey, Edgar Dobriban, Hamed Hassani, George J. Pappas, Eric Wong
- **ArXiv:** arXiv:2310.08419
- **Date:** October 2023
- **Type:** Attack Paper (LLM-Based)
- **Venue:** ICLR 2024

## Summary

Uses an LLM to iteratively refine jailbreak prompts. Achieves jailbreaking in twenty queries or less without requiring access to model internals. Black-box approach.

## Key Insights

1. **Black-Box**: No gradient or internal model access required.

2. **Query Efficiency**: Average of under 20 queries to successful jailbreak.

3. **Automated**: Fully automated prompt refinement.

4. **Multi-Turn**: Uses multiple refinement iterations.

## Research Approach

### Algorithm

1. **Generate**: Use attacker LLM to generate candidate prompt
2. **Evaluate**: Test against target model
3. **Refine**: Use feedback to improve prompt
4. **Iterate**: Repeat until success or query limit

## Key Innovation

Uses the target model itself as feedback:
- Target response informs next iteration
- No manual evaluation needed
- Automatic refinement loop

## Results

- Typical success in <20 queries
- Works on various models
- Black-box applicable

## Advantages

- **No Model Access**: Works on API-only models
- **Query Efficient**: Few queries needed
- **Automatic**: No human in loop
- **Versatile**: Works across model types

## Similar Work

- AutoDAN (similar LLM-based refinement)
- AutoAdv (multi-turn variant)

## Key Finding

LLMs can effectively attack other LLMs without any internal knowledge, using only input-output access.

## Implications

- API models are vulnerable to LLM-based attacks
- Need for API-level protections
- Red-teaming can be automated