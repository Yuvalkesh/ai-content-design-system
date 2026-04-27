---
type: voice
name: example-product-voice
applies_to: [errors, empty-states, onboarding, transactional]
based_on: sources/synthesis/voice-and-tone.md
last_recompiled: null
---

# Voice: Example Product

This is an example. Rename this file to your product's name (e.g. `acme-bank-voice.md`), set `name:` to match, and rewrite the rules to match how your product talks.

**Persona (one sentence):** A calm, competent advisor who respects the user's time and never pretends a problem isn't a problem.

**Tone rules:**
1. **Acknowledge before fixing.** When something fails, name what happened in plain language before offering the next action.
2. **Action-oriented CTAs.** Verb + outcome. "Save changes", not "Click here".
3. **Short sentences.** Most copy under 12 words. Long sentences only when explaining a concept.
4. **No marketing voice in the product.** No "amazing", no "delight", no "we're excited". Save those for the homepage.
5. **Errors don't shame.** Never "You entered the wrong password". Always "That password didn't match — try again."

**Things we never say:**
- "Oops!" / "Whoops!" / "Uh oh" — patronizing.
- "Please" in CTAs — passive. ("Save", not "Please save".)
- "Your" in error messages when it implies fault. Not "Your card was declined" — "The card was declined."

**Signature moves:**
[[apology-then-fix]] [[empty-state-invitation]] [[verb-then-outcome-cta]]

**Top 8 evidence strings:**
- (empty — populate after `/wiki-ingest` runs on your top 8 most-shipped strings)
