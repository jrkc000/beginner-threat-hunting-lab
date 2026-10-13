# Beginner Threat Hunting Lab: The Odd PowerShell Launch

**Difficulty:** Beginner  
**Type:** Endpoint + DNS/proxy + authentication log review  
**Environment:** Fully synthetic; no real malware, credentials, or external infrastructure  
**Estimated time:** 45–90 minutes  
**Tools:** Spreadsheet app, text editor, or Python (optional)

## Your role

You are a junior threat hunter reviewing a small set of telemetry from a fictional Windows workstation, `WS-014`, after an analyst noticed an unusual PowerShell process. Your task is to determine whether the activity is benign, suspicious, or likely malicious, and explain what evidence supports your conclusion.

## Scenario

At 09:00 on 2026-10-12, the help desk reported that user `a.sharma` saw a brief command window on workstation `WS-014`. No confirmed compromise has been declared. You have been given a small export of endpoint process events, PowerShell events, DNS/proxy activity, and authentication events covering the surrounding period.

The logs are intentionally incomplete, as real telemetry often is. Treat timestamps as local time (UTC+05:30) and correlate records using host, user, timestamp, process ID, and destination.

## Your mission

1. Read the files in `evidence/` and identify what is normal versus unusual.
2. Form one or two hunt hypotheses before drawing conclusions.
3. Search for related activity across the available logs.
4. Build a timeline of the most relevant events.
5. Decide whether the evidence supports benign activity, suspicious activity, or likely malicious activity.
6. Recommend sensible next steps. Do not claim facts that the logs do not establish.

## Questions to answer

- Which process or command first caught your attention, and why?
- What process launched it? Is the parent-child relationship expected?
- Was PowerShell used in an unusual way?
- Did the workstation resolve or contact any destination worth investigating?
- Do authentication events add context, or are they unrelated?
- What is your confidence level, and what evidence would you collect next?
- What detection or hunting query would you write to find similar activity?

## Evidence files

- `endpoint_process.csv` — process creation events, including parent process and command line.
- `powershell_events.csv` — selected PowerShell operational events.
- `dns_proxy.csv` — DNS lookups and web proxy requests.
- `authentication.csv` — selected sign-in events.

## Important limitations

- All records are fabricated for training.
- The dataset does not prove that a real system was compromised.
- A domain, command-line flag, or failed login is not conclusive by itself.
- Do not execute commands from the logs. They are evidence to inspect, not instructions to run.
- This lab focuses on investigation and reasoning, not malware execution or exploitation.

## Suggested workflow

1. Record the time range and systems/users in scope.
2. Write a hypothesis, such as: “If the PowerShell activity is suspicious, I expect to find an unusual parent process and network activity close in time.”
3. Filter and correlate the CSV files.
4. Document evidence with timestamps and source filenames.
5. Write a concise conclusion, caveats, and next steps.
6. Complete `hunt-report-template.md` and publish your write-up alongside the evidence, if desired.
