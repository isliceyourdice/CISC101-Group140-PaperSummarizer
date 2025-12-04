02_section_loop

1. Change Log: initial version created by meta-prompt.

2. Initialize loop: Iterate through normalized requested sections in the exact user-specified order.

3. Guardrail check: For each section, consult Module 3 to confirm permissibility:
   - If missing or empty: record “Section skipped: no usable text was provided.”
   - If very short (<50 words): record “Section very short: summary may be incomplete.”
   - If evidence_mode = strict and text lacks claims/results: record strict evidence limitation notice.

4. Summary mode selection: Based on summary_level:
   - short: produce a compact 1–2 sentence summary using only the section text.
   - detailed: produce a brief paragraph (3–5 sentences) plus 3–5 bullet points of key findings, methods, or contributions as applicable.

5. Cap enforcement: Ensure each section summary ≤ per_section_caps (default 150 words). If over cap, refine by removing redundancy, examples, and peripheral detail while preserving core facts.

6. Evidence discipline: Include only claims, equations, and results present in the text. If insufficient detail under strict mode, insert: “The source text does not provide enough detail to summarize this section in strict evidence mode.”

7. Record outputs: Store the final summary, any warnings, and a short section description (1-line essence) for the Section by Section Table.

