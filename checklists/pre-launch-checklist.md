# Pre-Launch Security Checklist

> Use this checklist before shipping any AI agent feature to production.

## System Prompt & Architecture

- [ ] System prompt explicitly addresses injection attempts
- [ ] System prompt uses clear delimiters for untrusted content (e.g., XML tags)
- [ ] System prompt defines what the agent should NOT do (not just what it should do)
- [ ] Each agent has the minimum set of tools required (least privilege)
- [ ] Inter-agent communication uses structured formats (not free text)
- [ ] Agent architecture is documented and reviewed by at least two team members

## Input Handling

- [ ] All input channels are documented (see [Attack Surface Map](../chapters/01-attack-surface-map.md))
- [ ] Each input channel has a defined risk level
- [ ] Input sanitization is in place for high-risk channels
- [ ] Input validation checks format/type before processing
- [ ] Maximum input lengths are enforced
- [ ] File upload types are restricted to expected formats

## Tool & Execution Controls

- [ ] Every tool with side effects has been reviewed for blast radius
- [ ] Destructive actions require user confirmation
- [ ] Tool call rate limiting is configured
- [ ] Tool parameters are validated against expected schemas
- [ ] There is an allowlist (not blocklist) for permitted tool actions
- [ ] Error messages don't leak system internals

## Output & Response Controls

- [ ] Responses are checked for system prompt leakage
- [ ] Output format is validated before delivery
- [ ] No raw tool output is exposed to users unless intentional
- [ ] Fallback responses exist for when the agent is confused or potentially compromised

## Monitoring & Incident Response

- [ ] All tool calls are logged with full parameters
- [ ] Inter-agent messages are logged
- [ ] Alerting is configured for anomalous patterns
- [ ] Incident response plan exists (see [Incident Response Template](incident-response-template.md))
- [ ] There is a kill switch to disable the agent feature quickly
- [ ] Log retention policy is defined

## Testing

- [ ] Basic injection attempts tested against all input channels
- [ ] Tested with adversarial user uploads (documents with embedded instructions)
- [ ] Tested multi-step injection scenarios
- [ ] Tested behavior when the agent encounters ambiguous or conflicting instructions
- [ ] Tested graceful degradation when external services are unavailable
- [ ] Edge cases for each tool have been identified and tested

## Team Readiness

- [ ] At least two team members understand the full agent architecture
- [ ] On-call rotation knows how to disable the agent feature
- [ ] Escalation path is defined for suspected injection incidents
- [ ] First audit date is scheduled

---

**Sign-off:**

| Role | Name | Date | Approved |
|------|------|------|----------|
| Product Lead | | | ☐ |
| Engineering Lead | | | ☐ |
| Security Review | | | ☐ |
