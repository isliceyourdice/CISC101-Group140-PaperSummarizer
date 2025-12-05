# 03_guardrails.md

Change Log:
- Added evidence_mode = "strict" and standardized warning messages for missing and short sections for PS3 Set 3.

## Module 3: Guardrails

1. Inputs  
   Receive from Module 1:  
   - section texts and normalized section names  
   - evidence_mode ("default" or "strict")  
   - summary_level  
   - per section word caps  

2. Check section availability  

   a. Missing or empty section text  
   - If a section has no usable text, mark it as not allowed for summarization.  
   - Output the standardized warning:  
     **"Section skipped: no usable text was provided."**

   b. Very short section (under 50 words)  
   - If section text exists but is under 50 words, mark it as very short.  
   - Output the standardized warning:  
     **"Section very short: summary may be incomplete."**  
   - Allow Module 2 to continue summarizing unless evidence_mode is "strict" and there is not enough evidence for a safe summary.

3. Evidence rules  

   a. Default evidence_mode  
   - Summaries should stay close to the text and avoid speculation.  

   b. Strict evidence_mode  
   - When evidence_mode is set to `"strict"`:  
     - Summaries must use only claims, equations, and results that clearly appear in the provided text.  
     - No extrapolation or guessing is allowed.  

   c. Insufficient information in strict mode  
   - If there is not enough information in a section to produce a safe strict summary, output:  
     **"The source text does not provide enough detail to summarize this section in strict evidence mode."**  
   - Instruct Module 2 to skip any normal summary for that section and use this message instead.

4. Interaction with Module 2  

   - For each section, return either:  
     - permission to summarize, or  
     - a specific warning message.  
   - Module 2 uses this information to decide whether to generate a summary or to only record the warning.  
   - All warnings must be passed forward to Module 4 so they appear in the Checks and Warnings section and next to the relevant section in the Section by Section Table.

5. Outputs  

   - A list of guardrail results for each section, including:  
     - whether summarization is allowed  
     - any standardized warning messages to display.
