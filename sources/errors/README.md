# sources/errors/

Drop your shipped error messages here. One file per error string.

**Format per file:**

```
context: Shown when payment fails on checkout. User has tried twice.
shipped: 2026-04-27
---
We couldn't charge that card. Try a different one — your cart's still here.
```

The wiki ingests **from** this folder. Don't write here from `/wiki-*` commands — this is your immutable archive.
