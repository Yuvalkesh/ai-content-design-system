---
type: lesson
name: no-invented-details
applies_to: [errors, empty-states, onboarding, transactional]
severity: hard
source_event: null
last_violated: null
---

# Never invent details about the system

**Rule:** Never write copy that describes system behavior the AI hasn't verified. Don't promise an email "in the next 24 hours" if you haven't checked the actual SLA. Don't say "your data is encrypted" if the engineer hasn't confirmed. Don't hallucinate features.

**Why:** Product copy is a contract. Invented details become liabilities — legal, support, trust. The user trusts the screen. If the screen lies, the relationship breaks.

**How to apply:** Before drafting anything that promises a behavior, timeframe, or capability — ask the PM. If you can't confirm, write around it. Vague but true beats specific but false.
