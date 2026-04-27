---
type: lesson
name: never-blame-user
applies_to: [errors, onboarding, transactional]
severity: hard
source_event: null
last_violated: null
---

# Never blame the user

**Rule:** Error and validation messages must never imply the user did something wrong. Even when they did.

**Why:** The user is already stuck — the screen is the only thing they're talking to. Adding blame to that conversation is the fastest way to lose them. The system can absorb the blame (or stay neutral) without losing accuracy.

**How to apply:**
- Replace "You entered the wrong X" → "That X didn't match — try again."
- Replace "Your card was declined" → "The card was declined by your bank."
- Replace "You can't do that" → "That action isn't available here."
- Validation: don't lecture. Just show what's needed. "Email format: name@domain.com" beats "You forgot the @ sign".
