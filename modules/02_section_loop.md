# 02_section_loop.md

Change Log:
- Updated module to add summary_level modes ("short" and "detailed") and to coordinate with strict evidence guardrails for PS3 Set 3.

## Module 2: Section Loop

1. Inputs  
   Receive from Module 1:  
   - normalized list of requested sections  
   - section texts  
   - audience  
   - per section word caps  
   - summary_level ("short" or "detailed")  
   - evidence_mode  

2. Iterate over sections  
   For each requested section, follow these steps in order:

   a. Guardrail check  
      - Ask Module 3 whether the section is missing, empty, very short, or restricted by strict evidence.  
      - If Module 3 returns a warning that the section should be skipped, record the warning and do not summarize that section.

   b. If section text is usable  
      - Respect the per section word cap from the specification.  
      - Use only information that appears in the section text.  
      - Do not add external facts or invented details.

3. Apply summary_level behavior  

   **If summary_level = "short":**  
   - Produce a compact 1 to 2 sentence summary of the section.  
   - The summary should capture the main idea only.  
   - Stay within the word cap.

   **If summary_level = "detailed":**  
   - First, produce a short paragraph summarizing the section.  
   - Then, produce a bullet list of 3 to 5 key points from the section text.  
   - Key points can include methods, results, contributions, or important definitions.  
   - All content must come from the source text.

4. Length and evidence checks  
   - If the draft summary exceeds the word cap, shorten it by removing repetition and less important details while keeping the main facts.  
   - If evidence_mode is "strict" and there is not enough information to support a safe summary, rely on Module 3 to output a strict evidence warning instead of forcing a summary.

5. Outputs  
   - For each section, return:  
     - the final summary (short or detailed), or  
     - the guardrail warning message from Module 3.  
   - Pass all section outputs to Module 4 so they can be rendered in the correct order in the final Paper Summary and Section by Section Table.
