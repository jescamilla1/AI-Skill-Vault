# Pine Script Claude Skill

> Turn Claude into a senior Pine Script developer. Describe a trading idea, get production-ready code.

---

## What This Is

Most traders can describe what they want. Few can write it in Pine Script. This skill bridges that gap — it gives Claude the knowledge, structure, and quality standards of an experienced Pine Script developer so you can vibe code your way to working indicators and strategies without fighting syntax errors, repainting bugs, or spaghetti logic.

This is not a single prompt. It's a modular skill system built across multiple reference files covering language fundamentals, strategy architecture, risk management, code quality standards, and a living bug tracker. Claude reads only what it needs for your task.

---

## What It Can Do

- Write indicators, strategies, and libraries from a plain English description
- Debug and fix broken scripts — explains the root cause, not just the symptom
- Build complete strategy systems with signal logic, filters, and risk management
- Prevent repainting and lookahead bias by default
- Teach Pine Script concepts with minimal examples and real-world application
- Convert v4 scripts to v5/v6
- Produce TradingView-publishable code with proper structure and documentation

---

## How to Use

### Claude Projects
1. Open or create a Project in [Claude.ai](https://claude.ai)
2. Upload all files from this folder into the Project
3. Start describing your trading idea — no special commands needed

### Clawhub
Available directly on Clawhub — install in one click:
👉 [clawhub.ai/alradyin/pinescript-mastery](https://clawhub.ai/alradyin/pinescript-mastery)

---

## Example Prompts

```
"Write an EMA crossover strategy with ATR-based stop loss and 2:1 R:R"
"My script is repainting on higher timeframe data, here's the code"
"Build a multi-timeframe RSI divergence indicator with alerts"
"Convert this v4 script to v5"
"How does request.security() work and when does it repaint?"
"Create a volume-weighted momentum strategy for crypto, 4H timeframe"
```

---

## File Structure

```
pinescript-claude-skill/
├── SKILL.md               # Entry point — execution protocol and file router
├── language-mastery.md    # v5/v6 syntax, type system, execution model
├── strategy-design.md     # Signal stacks, entry/exit patterns, backtesting rules
├── risk-management.md     # Position sizing, SL/TP systems, drawdown control
├── quality-standards.md   # Code structure, anti-patterns, publication checklist
├── indicators-library.md  # 30+ indicator implementations
└── known-bugs.md          # Verified Pine Script bugs with root cause and fix
```

---

## Origin & Credits

This skill is based on **Pinescript Mastery** by [@alradyin](https://clawhub.ai/u/alradyin), originally published on [Clawhub](https://clawhub.ai/alradyin/pinescript-mastery).

The original skill established the core execution protocol, reference architecture, and quality standards. This version extends it with additional bug documentation, Claude Projects compatibility, and ongoing improvements contributed through real development use.

Licensed under [MIT-0](https://spdx.org/licenses/MIT-0.html) — free to use, modify, and redistribute.

---

## Contributing

Found a Pine Script bug not in `known-bugs.md`? Open an issue with:
- Version affected (v5 / v6)
- Symptom
- Root cause
- Before/after fix

Confirmed bugs get added to the tracker so Claude never repeats them.
