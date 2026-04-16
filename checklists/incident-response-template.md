# Incident Response Template

> Use this template when you suspect a prompt injection has occurred in your agent system.

## Immediate Actions (First 30 Minutes)

### 1. Assess & Contain
- [ ] Identify the affected agent(s) and input channel(s)
- [ ] Determine if the injection is ongoing or a one-time event
- [ ] If ongoing: disable the affected input channel or pause the agent feature
- [ ] Notify the on-call engineer and product lead

### 2. Preserve Evidence
- [ ] Export relevant logs (tool calls, agent inputs/outputs, inter-agent messages)
- [ ] Screenshot any observable anomalous behavior
- [ ] Record the timestamp window of the suspected incident
- [ ] Do NOT modify or redeploy the system until evidence is preserved

## Investigation (First 2 Hours)

### 3. Trace the Attack Path
- [ ] Identify the injection entry point (which input channel?)
- [ ] Identify the injected content (what was the payload?)
- [ ] Trace which agents processed the injected content
- [ ] Determine which tools were called as a result
- [ ] Assess the blast radius: what data was accessed, modified, or exfiltrated?

### 4. Impact Assessment

| Question | Answer |
|----------|--------|
| Was user data exposed? | |
| Was data modified or deleted? | |
| Were external systems affected? | |
| How many users were impacted? | |
| Is the vulnerability still exploitable? | |
| Was this an isolated incident or part of a pattern? | |

## Remediation

### 5. Fix
- [ ] Patch the specific vulnerability that allowed the injection
- [ ] Test the fix against the original attack payload
- [ ] Test the fix against variations of the attack
- [ ] Deploy the fix to production

### 6. Verify
- [ ] Confirm the attack vector is no longer exploitable
- [ ] Monitor logs for similar patterns over the next 48 hours
- [ ] Verify no persistence mechanisms were established (modified files, altered configs)

## Post-Incident

### 7. Communicate
- [ ] Internal notification to relevant stakeholders
- [ ] If user data was exposed: follow your data breach notification process
- [ ] Update your threat model with the new attack vector

### 8. Learn
- [ ] Conduct a blameless post-mortem within 1 week
- [ ] Document: what happened, why it happened, how it was detected, how it was fixed
- [ ] Identify systemic improvements (not just fixing this one bug)
- [ ] Update the [Pre-Launch Checklist](pre-launch-checklist.md) with new items based on learnings
- [ ] Schedule a follow-up audit

## Post-Mortem Template

```markdown
# Post-Mortem: [Incident Title]
**Date of incident:** YYYY-MM-DD
**Date of post-mortem:** YYYY-MM-DD
**Severity:** Critical / High / Medium / Low

## Summary
[2-3 sentence summary of what happened]

## Timeline
- HH:MM — [event]
- HH:MM — [event]
- HH:MM — [detection]
- HH:MM — [containment]
- HH:MM — [resolution]

## Root Cause
[What fundamental issue allowed this to happen?]

## Impact
[What was affected? Users, data, systems?]

## What Went Well
- [thing that worked]

## What Went Poorly
- [thing that didn't work]

## Action Items
| Action | Owner | Deadline | Status |
|--------|-------|----------|--------|
| | | | |

## Lessons Learned
[What should we do differently going forward?]
```
