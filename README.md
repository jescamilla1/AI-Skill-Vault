# AI-Skill-Vault

> Production-grade AI skills for agents and Claude. Drop in, get results.

Skills are structured prompt systems — not single prompts. Each skill is a modular architecture that transforms an AI into a domain expert: enforcing standards, catching known bugs, applying professional methodology, and delivering consistent output quality.

---

## How to Use

### Claude Projects
1. Open or create a Project in Claude.ai
2. Upload all files from the skill folder into the Project
3. Start chatting — the skill activates automatically

### Clawhub / Agent Platforms
1. Point your agent at the skill's `SKILL.md` as the entry point
2. The skill router instructs the agent which reference files to load per task
3. Files load on demand — only what the task needs

---

## Skills

| Skill | Domain | Status |
|---|---|---|
| [Pinescript Claude Skill](./Pinescript%20Claude%20Skill/) | TradingView / Pine Script v5 & v6 | `v1.0.0` |

---

### 🌲 Pinescript Claude Skill
Turns Claude into a senior Pine Script developer. Write indicators, strategies, and libraries with production structure, risk management, repainting prevention, and verified bug fixes — from a simple idea or existing broken code.

---

## Built with this skill

[`Harmonic Detection/`](./Harmonic%20Detection/) — a harmonic chart-pattern
indicator (`Harmonic.pine`) plus its supporting technical-analysis library
(`TA.pine`), built using the Pinescript Claude Skill above. See
[the writeup](https://jescamilla1.github.io/articles/harmonic-patterns.html)
for what it does and why it was built from scratch instead of an existing
library.

---

## Architecture Notes

**Why modular files instead of one big prompt?**
Context budget. A monolithic prompt loads everything on every message. Modular files let the agent load only what the task needs — reducing noise and keeping responses focused.

**Why a Known Bugs file per skill?**
Bugs found during development are documented with root cause and fix. The execution protocol checks this file before validating any output. Same mistake never surfaces twice.

**Two deployment modes**
Skills are structured for both Claude Projects (flat files, context injection) and agent platforms like Clawhub (hierarchical, lazy loading). Same content, different structure.

