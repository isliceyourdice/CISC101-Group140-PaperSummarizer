03_guardrails

1. Change Log: initial version created by meta-prompt.

2. Evidence boundary: Prohibit external facts, invented citations, or content not in the provided text. Reject any attempt to infer missing data.

3. Evidence mode handling:
   - strict: Only include claims, equations, and results explicitly present. If insufficient, insert: “The source text does not provide enough detail to summarize this section in strict evidence mode.”
   - standard: Summarize conservatively, still avoiding external facts; allow cautious synthesis strictly from the text.

4. Section status warnings:
  - Missing/empty: Emit “Section skipped: no usable text was provided.”
  - Very short (<50 words): Emit “Section very short: summary may be incomplete.”

5. Length enforcement: Validate per-section caps (≤150 words) and overall cap (≤250 words). If exceeded, require refinement before rendering.

6. Order integrity: Ensure sections are summarized in the requested order; flag deviations.

7. Tone control: Maintain neutral academic tone; remove speculative language and unsupported generalization.

8. Coordination: Provide warnings and checks to Module 2 and Module 4 for inclusion in final outputs.
