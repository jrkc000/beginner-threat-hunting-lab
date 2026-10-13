# Threat Hunting Report — [Case Name]

> **Lab:** Beginner Threat Hunting Lab: The Odd PowerShell Launch  
> **Analyst:** [Your name / GitHub handle]  
> **Date:** [YYYY-MM-DD]  
> **Status:** [In progress / Complete]  
> **Classification:** [Benign / Suspicious / Likely malicious / Inconclusive]

## 1. Executive summary

Write 3–5 sentences for a technical or non-technical reader. State what you investigated, your main finding, and your confidence.

## 2. Scope

- **Time range reviewed:** 
- **Host(s):** 
- **User/account(s):** 
- **Data sources reviewed:** 
- **Out of scope / unavailable telemetry:** 

## 3. Hunt hypothesis

State a testable hypothesis before describing the results.

**Hypothesis:**  
[Example structure: If ___ is occurring, I expect to observe ___ in ___ logs.]

**Why this hypothesis is worth testing:**  
[Briefly explain the signal or concern that led you here.]

## 4. Investigation method

List the steps you took and how you correlated records. Mention any tools used (for example, Excel filters, `grep`, or a Python script).

1. 
2. 
3. 

## 5. Findings

### Finding 1 — [Short title]

- **Observation:** 
- **Evidence source and timestamp:** 
- **Why it matters:** 
- **Alternative benign explanation:** 
- **Confidence:** [Low / Medium / High]

### Finding 2 — [Short title]

- **Observation:** 
- **Evidence source and timestamp:** 
- **Why it matters:** 
- **Alternative benign explanation:** 
- **Confidence:** [Low / Medium / High]

_Add or remove findings as needed. Distinguish observed facts from interpretation._

## 6. Timeline

| Timestamp (local) | Host / account | Event | Source file | Significance |
|---|---|---|---|---|
| YYYY-MM-DD HH:MM:SS | | | | |

## 7. Indicators and artifacts

| Type | Value | Evidence source | Assessment / caveat |
|---|---|---|---|
| Host | | | |
| User/account | | | |
| Process / command | | | |
| Domain / IP | | | |
| File path | | | |

Do not label an indicator malicious solely because it looks unusual. Explain the context and confidence.

## 8. Conclusion

- **Assessment:** [Benign / Suspicious / Likely malicious / Inconclusive]
- **Confidence:** [Low / Medium / High]
- **Strongest supporting evidence:** 
- **Evidence that is missing or ambiguous:** 
- **What I cannot conclude from this dataset:** 

## 9. Recommended next steps

Prioritize practical defensive actions. Examples: preserve endpoint evidence, review the referenced file, collect fuller PowerShell logs, check whether the domain appears on other endpoints, or validate service-account use with the system owner.

1. **Immediate:** 
2. **Follow-up hunt:** 
3. **Prevention / detection improvement:** 

## 10. Detection idea

Describe a query or detection logic that could find similar behavior. Pseudocode is fine; do not claim it was tested if it was not.

```text
WHEN process_name is powershell.exe
AND parent_process is an unexpected Office application
AND command_line contains suspicious execution flags
THEN investigate related process, script, DNS, proxy, and authentication events
```

**Potential false positives:**  
**Tuning ideas:**  

## 11. Lessons learned

- What clue was most useful?
- What took the most time?
- What would you investigate differently with more telemetry?

## 12. Evidence references

List the exact filenames and the records you relied on.

- `evidence/endpoint_process.csv` — 
- `evidence/powershell_events.csv` — 
- `evidence/dns_proxy.csv` — 
- `evidence/authentication.csv` — 

## 13. Reproducibility

- **Tools / versions:** 
- **Filters or commands used:** 
- **Limitations:** 

---

### Publication checklist

- [ ] No real personal data, secrets, or credentials included.
- [ ] Facts and assumptions are clearly separated.
- [ ] Every major claim points to evidence.
- [ ] False positives and limitations are discussed.
- [ ] The conclusion is proportional to the evidence.
- [ ] Any query is labelled as pseudocode if not tested.
