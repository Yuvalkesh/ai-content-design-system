---
type: pattern
name: apology-then-fix
status: active
applies_to: [errors, transactional]
evidence_count: 0
avg_perf: {}
top_examples: []
last_lint: null
---

# Apology-then-fix

**Definition:** Open the error with a brief acknowledgment of what failed, then immediately offer the user's next step. Two beats, in that order.

**When to use:**
- Default for any error message where the user's action triggered the failure (declined cards, failed uploads, wrong passwords).
- When the user might reasonably blame themselves.

**When NOT to use:**
- System-side errors with no user action (use `system-status-then-eta` pattern instead).
- Errors where the next step isn't immediately obvious (use `error-with-help-link` pattern).

**Variations:**
- Tight (under 8 words): "Card declined. Try a different one."
- Standard: "We couldn't charge that card. Try a different one — your cart's still here."
- Empathetic: "That didn't work. Card was declined by your bank. Try another card."

**Backlinks:** [[example-product-voice]] [[never-blame-user]]
