05_key_contributions_summarizer

Change Log: initial version created by meta-prompt.

1. Input scope: Receive the paper text and per-section outputs from Modules 2 and 3.

2. Identify contributions: Extract main contributions and innovations explicitly stated in the paper (e.g., architectural novelty, training efficiency, empirical gains) without adding external claims.

3. Evidence link: Connect each contribution to the reported methods/results within the provided text (benchmarks only if present; do not invent).

4. Summarize succinctly: Produce a compact list:
   - 3–6 bullet points, each stating the contribution and the supporting evidence or result from the text.

5. Cap compliance: Keep the entire contributions summary ≤200 words.

6. Guardrails: If evidence_mode = strict and data are insufficient, include: “The source text does not provide enough detail to list key contributions in strict evidence mode.”

7. Hand-off: Provide this contributions summary to Module 4 for incorporation into the Paper Summary or as an optional insert.
