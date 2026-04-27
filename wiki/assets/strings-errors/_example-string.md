---
type: string
surface: errors
date: 2026-04-15
status: shipped
voice: example-product-voice
patterns: [apology-then-fix]
hooks: []
themes: [first-time-user]
context: Shown when payment fails on checkout. User has tried twice.
source: ../../../sources/errors/2026-04-15-checkout-card-declined.md
---

# Example string: checkout — card declined

This is an example asset entity. Each shipped string becomes one of these — light frontmatter pointing at the patterns/hooks/themes it uses, plus a short body explaining why it worked or what tradeoff was made.

**The string (as shipped):**

> We couldn't charge that card. Try a different one — your cart's still here.

**Why it works:**
- Acknowledges the failure without blaming the user (`apology-then-fix` pattern, `never-blame-user` lesson).
- Reassures the cart is intact — reduces panic.
- Direct CTA in the second clause, no "please".

**Notable choices:**
- "We couldn't charge" instead of "Your card was declined" — system absorbs the action.
- "Try a different one" instead of "Try again" — implies the previous card won't work.
- "Your cart's still here" — anti-anxiety phrase, no equivalent in the design system yet but should be.
