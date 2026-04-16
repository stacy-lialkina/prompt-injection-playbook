# 🛡️ Prompt Injection Playbook

**A practical guide to prompt injection risks in AI agent systems — written for product managers, architects, and teams shipping AI-powered products.**

> This playbook is born from hands-on experience building multi-agent systems in production. It focuses on *what to do about it*, not just *what can go wrong*.

---

## Why This Exists

AI agents are shipping fast. They browse the web, read files, execute tools, and talk to APIs. Every one of those capabilities is a surface for prompt injection — where untrusted content hijacks the agent's behavior.

Most security resources on this topic are either too academic or too code-heavy. This playbook bridges the gap: it's for people who **design and ship AI products** and need to make practical risk decisions.

## Who It's For

- **Product managers** scoping AI features and assessing risk
- **Architects** designing multi-agent systems
- **Engineering leads** reviewing agent pipelines
- **Anyone** evaluating third-party AI tools or plugins

## What's Inside

### 📖 Chapters

| # | Chapter | What You'll Learn |
|---|---------|-------------------|
| 1 | [Attack Surface Map](chapters/01-attack-surface-map.md) | Where injections enter your system — every input channel ranked by risk |
| 2 | [Anatomy of an Attack](chapters/02-anatomy-of-an-attack.md) | How prompt injections actually work, with real-world patterns |
| 3 | [Multi-Agent Risks](chapters/03-multi-agent-risks.md) | Why multi-agent architectures multiply the attack surface |
| 4 | [Community Skills & Plugins](chapters/04-community-skills-and-plugins.md) | The hidden danger of community-contributed agent extensions |
| 5 | [Defense Patterns](chapters/05-defense-patterns.md) | Practical mitigation strategies that work today |
| 6 | [Audit Playbook](chapters/06-audit-playbook.md) | Step-by-step process for auditing an existing agent system |

### ✅ Checklists

- [Pre-Launch Security Checklist](checklists/pre-launch-checklist.md) — before you ship an agent feature
- [Skill/Plugin Audit Checklist](checklists/skill-audit-checklist.md) — before you install a community extension
- [Incident Response Template](checklists/incident-response-template.md) — when something goes wrong

### 🧪 Examples

- [Injection Patterns Catalog](examples/injection-patterns.md) — categorized examples of injection techniques
- [Safe vs Unsafe Architecture Comparison](examples/architecture-comparison.md) — side-by-side design decisions

## Key Principles

This playbook is built on four ideas:

1. **Treat all external content as untrusted.** Files, web pages, API responses, user uploads — anything the agent reads that you didn't write is an attack vector.
2. **Least privilege by default.** An agent should only have the tools and permissions it needs for the current task.
3. **Defense in depth.** No single layer stops all injections. Layer input filtering, output validation, sandboxing, and human-in-the-loop controls.
4. **Design for failure.** Assume injections will sometimes succeed. Limit blast radius. Log everything. Make rollback easy.

## How to Use This

- **Starting a new AI product?** Read chapters 1 and 5 first, then use the pre-launch checklist.
- **Already shipped and worried?** Start with chapter 6 (Audit Playbook) and the checklists.
- **Evaluating plugins or skills?** Go straight to chapter 4 and the skill audit checklist.
- **Building multi-agent systems?** Chapter 3 is your starting point.

## Contributing

Found a new injection pattern? Have a defense that worked in production? PRs are welcome.

Please keep contributions practical and actionable. We're optimizing for "what should I do about this on Monday morning", not theoretical completeness.

## License

[MIT](LICENSE) — use it, share it, adapt it.

---

*Maintained by [Stacy Lialkina](https://github.com/stacy-lialkina) — Product lead building AI-powered products.*
