## git
- Don't commit, tag or push unless asked.
- Never use --no-verify.

## Writing code
<!---
Partially stolen from https://joecotellese.com/posts/claude-code-global-configuration/
-->

- Prefer simple, clean, maintainable solutions over clever or complex ones, even if the latter are more concise or performant. Readability and maintainability are primary concerns.
- You MUST ask permission before reimplementing features or systems from scratch instead of updating the existing implementation.
- When modifying code, match the style and formatting of surrounding code, even if it differs from standard style guides. Consistency within a file is more important than strict adherence to external standards.
- NEVER make code changes that aren't directly related to the task you're currently assigned. If you notice something that should be fixed but is unrelated to your current task, tell me about it instead of fixing it immediately.
- NEVER remove code comments unless you can prove that they are actively false. Comments are important documentation and should be preserved even if they seem redundant or unnecessary to you.
- When you are trying to fix a bug or compilation error or any other issue, YOU MUST NEVER throw away the old implementation and rewrite without expliict permission from the user. If you are going to do this, YOU MUST STOP and get explicit permission from the user.
- NEVER name things as 'improved' or 'new' or 'enhanced', etc. Code naming should be evergreen. What is new someday will be "old" someday.
- Help me become a better coder by explaining the "why" behind your implementation choices
- Use idiomatic coding patterns for each language - always confirm you're following language-specific best practices

## Code Comments
<!---
Partially stolen from https://gist.github.com/bavanws/123e0343f8a79cec825d9141124a0a83
-->

- Default to no comment. Code shows *how*; comment only to carry *why* — a non-obvious constraint, deliberate deviation, gotcha, or workaround.
- Never narrate the code ("loop over users", "parse the body"), restate names/types/signatures, or mark block ends.
- Never narrate the change ("fixed X", "updated to Y", "as requested"). A comment must read correctly to someone seeing the file fresh who never saw the diff; change context belongs in the commit message.
- Delete by default. A comment that just restates a decision the code already reflects — "1 vCPU is deliberate", "right-sized from prod" — is dead weight even when it points to a doc: the doc is where anyone questioning it looks anyway. Keep inline only what a reader needs *at that line* and can't get from the code — a non-obvious invariant/constraint ("timeout must stay < interval — ALB rule") or a cross-file sync obligation ("keep in sync with the router's TGs").
- Comments must stand on their own with any link removed — encode the substance, never a pointer as a substitute for it. Banned: specs, section numbers, design docs — point-in-time artifacts that get superseded and rot ("spec §7" is the canonical case). Fine: a maintained doc/README at a stable path — and when the *why* is a system-level narrative ("why it's built this way"), extract it there as a *pure* extraction: not an inline block, and not a comment that merely points to the doc. What stays inline are the non-obvious local details, which reference the doc only when a reader genuinely needs it *at that line* — a pointer-only comment generally shouldn't exist at all. Tickets, Confluence, RFCs, permalinks stay fine as trailing breadcrumbs.
- Occam's razor on every comment you *keep*, not just the ones you delete. "Carries a real *why*" and "is worded minimally" are independent judgments — a genuine *why* can still be 3x too long, and "it's a real why" is not license to keep the wording verbatim. Keep only the one non-obvious fact a reader needs *at that line*, in the fewest words; cut the mechanism the code already shows, where a value is consumed downstream, the consequence-of-the-consequence, and justification-of-the-justification. A 5-line block almost never survives intact — suspect it on sight; the razored answer is sometimes zero.
- A one-line summary on a public function/endpoint is fine; inline restatement of a single clear line never is.
- TODOs are fine and don't need issue IDs — but a TODO is a marker, not a substitute for doing the work in scope.
- When writing comments, avoid referring to temporal context about refactors or recent changes. Comments should be evergreen and describe the code as it is, not how it evolved or was recently changed.

### Small, Iterative Changes
- Work in small, testable increments - implement, test with human in the loop, then continue
- Make the smallest reasonable changes to achieve the desired outcome
- Break down work into small, iterable, testable chunks
- Always discuss plans before implementation unless explicitly told otherwise
