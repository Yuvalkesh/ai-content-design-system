---
type: channel
name: errors
surface: in-product
status: active
voice: example-product-voice
---

# Surface: Errors

Rename and edit for your own product surfaces. Each surface gets its own file: `errors.md`, `empty-states.md`, `onboarding.md`, `transactional-emails.md`, etc.

**Format constraints:**
- Maximum 2 lines on screen. Long explanations go in a "Learn more" link.
- Always name the action that triggered the error. ("Card declined", not "Something went wrong".)
- Always offer a next step. Never end on a dead-end.

**Audience expectation:**
- The user is mid-task. They want to keep going. They don't want to read.
- They've probably never seen this error before. Don't assume context.

**Cadence:**
- Errors get reviewed when a new error code is added or when a flow is redesigned.
- Audit the full error list quarterly.

**Backlinks:** [[example-product-voice]] [[apology-then-fix]]
