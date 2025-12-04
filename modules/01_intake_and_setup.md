01_intake_and_setup
1. Change Log: initial version created by meta-prompt.

2. Collect inputs: Acquire paper text or section excerpts; requested sections; audience type (expert or lay); per-section word caps; overall word cap; summary_level ("short" or "detailed"); evidence_mode ("strict" or "standard").

3. Normalize sections: Map user-provided section labels to canonical names: Introduction, Methods, Results, Discussion. Preserve order given by the user.

4. Partition text: If full paper text is provided, segment it into sections using headings and common cues; otherwise, use provided per-section excerpts as-is. Do not invent segments.

5. Presence check: For each requested section, mark status as present, missing, or empty. If fewer than 50 words, mark as very short.

6. Configuration: Set:
   - audience: expert or lay
   - per_section_caps: default ≤150 words unless user specifies lower caps
   - overall_cap: ≤250 words
   - summary_level: short (1–2 sentences) or detailed (short paragraph + 3–5 bullets)
   - evidence_mode: strict or standard (default to strict if unspecified)

7. Constraints registry: Record PS2 constraints (caps, order, tone, no external facts). Prepare a list of initial warnings for missing or very short sections.

8. Hand-off: Provide a structured bundle to Module 2 and Module 3 with: normalized sections, section texts, statuses, configuration, and initial warnings.
