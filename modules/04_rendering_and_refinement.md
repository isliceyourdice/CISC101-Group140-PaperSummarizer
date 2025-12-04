04_rendering_and_refinement

Change Log: initial version created by meta-prompt.

1. Assemble structure: Create the final output with the following labeled parts:
- Paper Summary (overall)
- Section by Section Table (requested sections + short descriptions)
- Expert Summary (≤250 words)
- Lay Summary (≤250 words)
- Mini Glossary (key terms from the paper)
- Checks and Warnings (missing sections, very short sections, strict evidence limitations, uncertainty notes)

2. Overall summaries:
- Expert Summary: Focus on objectives, architecture, methods, datasets/benchmarks (only if in text), quantitative results, and limitations. Respect the 250-word cap.
- Lay Summary: Explain the paper’s purpose, approach, and significance in accessible language. Respect the 250-word cap.

3. Mini Glossary: Extract 5–10 important terms from the paper (e.g., “self-attention,” “multi-head attention”) and provide concise definitions only based on the provided text.

4. Section by Section Table: For each requested section, list the section name and a 1-line description. Do not place citations in the table; keep them textual, if present in source.

5. Checks and Warnings: Aggregate all guardrail messages: missing/empty sections, very short sections, strict evidence limitations, and any uncertainty notes about incomplete information.

6. Refinement pass: Ensure all per-section summaries ≤150 words; overall summaries ≤250 words; remove redundancy; maintain neutral tone; confirm no external facts are introduced.

7. Final review: Verify order integrity and explicit list of sections covered. Confirm readability with short paragraphs and consistent formatting.
