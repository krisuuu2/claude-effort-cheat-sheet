# Claude effort level — cheat sheet

🇵🇱 Po polsku: [PL.md](PL.md)

**Effort doesn't make Claude smarter. The model decides how smart it is. Effort decides how much Claude checks its own work:** how many files it reads, how many tests it runs, and how many steps it takes before it comes back to you. (Anthropic: Lydia Hallie, Thariq Shihipar)

Change it in Claude Code with `/effort` (you can switch mid-conversation). Levels: `low` · `medium` · `high` · `xhigh` · `max`.

## Which level for which job

| Level | Use it for | Example |
|---|---|---|
| **low** | ideas, sketches, small edits, anything you'll look at right away | "draft 3 versions of this email", "rename these files" |
| **medium** | normal everyday work | a new feature, a script you'll review |
| **high** | anything where a mistake would cost you money, or where hidden edge cases exist | a bug in old code, totals in a spreadsheet you'll send to a client |
| **max** | long jobs Claude does on its own | build and test a whole app end to end |

## The routine Anthropic's engineer uses

1. Give Claude the task and ask it to **interview you** about the missing details.
2. **Build on low.**
3. **Review and fix on low** — fast loops, you correct it in a minute.
4. **Switch to high at the end** to verify and test everything.

## What the numbers say

- Same simple fitness app: **1.5 min on low, 67 min on max** (Anthropic's test).
- A security filter (HTML sanitizer): **1/5 on low → 5/5 on xhigh** — effort pays off on long jobs with hidden traps.
- My test (Opus 5.5, 3 runs each): a bank export with a double payment, a refund and an amount written with a comma. **Low: right 3/3. High: ~60% more output tokens, and 1 run interpreted the question differently.**
- More effort doesn't fix a misunderstood question. If the answer is wrong because Claude read the task differently, rewrite the prompt instead of raising effort.

## Quick rule

**Start on low. Raise it only when Claude skipped a file, skipped a test or didn't double-check — or when a mistake would cost you money.**

Sources: [Spending your effort — Thariq Shihipar](https://claude.dev/blog/spending-your-effort) · [Claude Code effort level and model selection — Lydia Hallie](https://claude.com/resources/articles/claude-model-and-effort-level-in-claude-code)

— @aipractically
