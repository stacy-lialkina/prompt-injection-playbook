# Skill / Plugin Audit Checklist

> Use this before installing any community-contributed skill, plugin, or extension for an AI coding agent.

## Source Evaluation

- [ ] Author/publisher is identifiable (not anonymous)
- [ ] Repository has meaningful commit history (not a single-commit repo)
- [ ] Repository has stars/forks/usage indicators
- [ ] Author has other legitimate public projects
- [ ] Skill has been mentioned or recommended by trusted sources
- [ ] Last updated within the past 6 months

## Content Review

- [ ] Read every file in the skill (not just the README)
- [ ] No unexpected URLs or external endpoints
- [ ] No instructions to "always" perform actions or "never" reveal information
- [ ] No references to sending, posting, or transmitting data externally
- [ ] No encoded content (Base64, hex) without clear explanation
- [ ] No shell commands that download or execute remote code
- [ ] No instructions referencing tools or permissions beyond the skill's stated purpose
- [ ] No hidden text (check for whitespace manipulation, zero-width characters)

## Behavioral Review

- [ ] The skill's stated purpose matches its actual content
- [ ] Instructions are scoped to a specific task (not broad behavioral overrides)
- [ ] No instructions that could override the agent's core safety behavior
- [ ] No instructions that reference or modify other skills/plugins
- [ ] No persistence mechanisms (writing files, modifying configs)

## Installation Decision

- [ ] Benefits clearly outweigh risks for your use case
- [ ] You've copied only the needed parts to your controlled directory (e.g., `~/.agents/`)
- [ ] You've recorded the audit in your audit log with date and findings
- [ ] You've set a reminder to re-review in 3 months

## Audit Log Entry

```
Date: YYYY-MM-DD
Skill: [name]
Source: [URL]
Version/Commit: [hash]
Decision: APPROVED / REJECTED / APPROVED WITH MODIFICATIONS
Notes: [what you found, any concerns, what you modified]
Reviewer: [your name]
Next review: YYYY-MM-DD
```
