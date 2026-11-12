# TEAM: 5 Claudes review your code before you ship it

A free prompt for Claude Code. A hacker, a confused user, a senior dev, a tester and a boss each check your code, then the boss gives one verdict (SHIP IT or NOT YET) and a fix list with file and line.

**Easiest way:** open the page and hit Copy: https://reggiejunior.github.io/team/

## Step 1: call the team
Paste this into Claude Code in your project and fill in the two [BRACKETS].

```text
You are a review panel of 5 experts checking my code before I ship it. Review only: do not change any files yet.

What the code does: [DESCRIBE IT IN ONE SENTENCE]
What to review: [THE FILES OR FOLDER, OR PASTE THE CODE HERE]

Each reviewer works on their own first, then reports.

1. THE HACKER tries to break in. Looks for secrets or API keys in the code, input that is never checked, injection (SQL, shell, prompt), missing login or permission checks, unsafe file and URL handling, and private data leaking into logs or error messages.

2. THE CONFUSED USER has never seen this app. Leaves fields empty, types letters where numbers go, pastes emoji, clicks twice, goes back mid-way, loses internet. Reports what breaks, what crashes and what is confusing.

3. THE SENIOR DEV reads it as if they have to maintain it for the next two years. Looks for unclear names, copy-pasted code, functions doing too much, errors that are swallowed, and things that will break as soon as there is more data or more users.

4. THE TESTER runs it. Runs the existing tests; if there are none, writes a few small tests for the most important paths and edge cases and runs them. Reports the exact command used and what passed or failed.

5. THE BOSS reads the four reports, removes duplicates and anything that is not a real problem, and gives ONE verdict: SHIP IT or NOT YET.

Rules for everyone:
- Every issue names the file and line, says what goes wrong, and gives a one-line fix.
- No vague advice ("consider improving error handling" is not allowed).
- Do not invent problems. If a reviewer finds nothing, they say so in one line.

The Boss's final answer, in this format:

VERDICT: SHIP IT / NOT YET

FIX LIST (most severe first)
1. [CRITICAL / HIGH / MEDIUM / LOW] file:line - what goes wrong - the fix

WHAT'S ALREADY GOOD (up to 3 points)
```

## Step 2: fix it and review again
When the boss says NOT YET, paste this in the same chat.

```text
Now fix everything on the Boss's fix list, starting with the most severe.
- Make the smallest change that fixes each issue. Do not rewrite code that works.
- After each fix, run the tests again.
- When you are done, run the full 5-reviewer panel again on the changed code and give me the new verdict and fix list.
- Repeat until the verdict is SHIP IT or only LOW items are left. Then stop and tell me what you changed and what is left.
```

> Commit your code first. The team only reviews; it cuts the risk a lot, but no review catches 100% of bugs.

---
More free prompts, skills and tools in the **[AI Library](https://www.skool.com/ai-library)**.
