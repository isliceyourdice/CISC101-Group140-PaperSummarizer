06_jargon_simplifier

Change Log: initial version created by meta-prompt.

1. Source selection: Identify technical sentences across sections (e.g., architecture, optimization, evaluation) that may hinder lay understanding.

2. Rewrite rules: Transform each sentence into plain language while preserving all factual content:
   - Replace domain-specific jargon with accessible terms.
   - Keep the original meaning and avoid external examples or analogies unless the text provides them.

3. Side-by-side output: For each item, output:
   - Original sentence (short)
   - Simplified sentence (short)

4. Caps and tone: Keep each simplified sentence ≤30 words; maintain neutral, factual tone; avoid speculative language.

5. Evidence adherence: Only simplify content present in the text; do not add facts or interpretations.

6. Integration: Provide simplified sentences to Module 4 to inform the Lay Summary and the Mini Glossary definitions.
