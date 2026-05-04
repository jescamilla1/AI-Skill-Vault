# Known Bugs — Pine Script

Confirmed bugs encountered during development. Each entry is verified before being added.

---

## BUG-001 — `timeframe` / `timeframe_gaps` in `indicator()` breaks with side effects

**Version affected:** v5

**Symptom**
Script with `bgcolor`, `barcolor`, `plot`, `plotshape`, `table`, `alertcondition`, `label`, or `line` throws an error or behaves incorrectly when `timeframe` or `timeframe_gaps` parameters are present in `indicator()`.

**Root Cause**
Pine Script does not allow `timeframe` or `timeframe_gaps` in `indicator()` when the script has side effects. The two features are incompatible at the declaration level.

**Before**
```pine
indicator("My Script", timeframe="D", timeframe_gaps=true)
plot(close)
```

**After**
```pine
indicator("My Script")
htf_close = request.security(syminfo.tickerid, "D", close, lookahead=barmerge.lookahead_off)
plot(htf_close)
```

**Discovered:** 2026-04

---

## BUG-002 — Multi-line ternary operators cause runtime errors

**Version affected:** v5 / v6

**Symptom**
Script throws a runtime error when a ternary operator is split across multiple lines.

**Root Cause**
Pine Script's parser does not support multi-line ternary expressions. The line break breaks the expression evaluation.

**Before**
```pine
color := condition
     ? color.green
     : color.red
```

**After**
```pine
color := condition ? color.green : color.red

// If expression is too long, pre-assign intermediate values:
val = condition ? long_expression_a : long_expression_b
color := val == something ? color.green : color.red
```

**Discovered:** 2026-04

---

## BUG-003 — `input.*()` tooltip must be a `const string` literal

**Version affected:** v5 / v6

**Symptom**
Compile error when tooltip argument contains string concatenation, `str.tostring()`, or any runtime expression.

**Root Cause**
Pine Script requires tooltip arguments to be compile-time constants. Any dynamic string construction fails at compile.

**Before**
```pine
rsi_len = input.int(14, "RSI Length",
     tooltip="Period: " + str.tostring(14))
```

**After**
```pine
rsi_len = input.int(14, "RSI Length",
     tooltip="Number of bars for RSI calculation.")
```

**Discovered:** 2026-04
