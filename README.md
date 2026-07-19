<p align="center">
  <img src="./logo.png" alt="accessible-output" width="140" />
</p>
<p align="center">
  <strong align="center">Action-first, explicit outputs for ADHD and autistic readers</strong>
</p>
## Install

Claude Code:

```bash
claude plugin marketplace add advatar/accessible-output
claude plugin install accessible-output@accessible-output
```

Codex:

```bash
codex plugin marketplace add advatar/accessible-output
codex plugin add accessible-output@accessible-output
```

Invoke it with `/accessible-output` in Claude Code or `$accessible-output` in Codex. Add a mode when needed: `/accessible-output adhd`, `/accessible-output autistic`, or `/accessible-output both`.

To disable in Claude Code: `claude plugin disable accessible-output` or use `/plugin disable accessible-output`.

More in [INSTALL.md](./INSTALL.md).

## What it does

A Claude Code and Codex skill for readers with ADHD, autism, or both. It makes responses easier to act on without assuming that every neurodivergent reader communicates the same way.

For ADHD, it reduces working-memory load: action first, bounded steps, visible progress, and one clear next move.

For autistic readers, it reduces ambiguity: assumptions, definitions, deadlines, choices, and fallback paths are stated instead of implied. The answer stays literal and predictable without forcing a social script or burying the action under background.

The combined pattern is: `Current state → Next action → Expected result → If blocked`.


## What changes


<table>
<tr>
<td width="50%">

## Before

> Great question! Let me think about this. Your auth flow has a few moving pieces: the middleware, the token verification, and the cookie handling. Looking at `src/auth.ts`, the `verifyToken` function (around lines 42-58) seems to be using an older `jsonwebtoken` API. One approach would be to update the package and rewrite that function. After making the change, you'd want to run the auth tests to confirm nothing breaks. By the way, you might also want to look at your dependency versions overall. Hope this helps! Let me know if you want to dig deeper.

</td>

<td width="50%">

## After

> Run `npm install jsonwebtoken@latest`, then edit `src/auth.ts:42`.
>
> 1. Open `src/auth.ts`
> 2. Replace `verifyToken` (lines 42–58) with the snippet below
> 3. Run `npm test -- auth.spec.ts`
>
> Next: paste the first failing line if any test fails.

</td>
</tr>
</table>

### Example: make an ambiguous model response predictable

User prompt: “Can you clean this up soon? Make it more professional, but keep the same vibe.”

**Model response before accessible-output**

> Sure! I can clean this up and make it more professional while keeping the same vibe. I’ll take a look and make the necessary changes. Let me know if you had something specific in mind!

**Model response with accessible-output**

> Next: revise `README.md` while preserving its friendly tone.
>
> 1. Fix grammar and sentence fragments
> 2. Replace slang with plain language
> 3. Preserve headings, examples, and meaning
>
> Deadline: no deadline was provided. Expected result: a diff limited to wording and grammar. If “professional” means a formal tone instead, choose that option before editing.

### Example: separate urgency from importance in a model response

User prompt: “This is important, so please deal with it ASAP. It shouldn’t take long.”

**Model response before accessible-output**

> This looks important, so I’ll prioritize it and get it sorted as soon as possible. It should be a quick fix.

**Model response with accessible-output**

> Priority: medium. No immediate action is required now.
>
> Next: spend about 15 minutes reproducing the bug today. The report is due Friday at 16:00. If reproduction fails, record the exact input and error message instead of guessing.


## The rules

12 rules. Full text in [SKILL.md](./skills/accessible-output/SKILL.md).

1. Lead with the next action.
2. Number multi-step tasks.
3. End with one concrete next step.
4. Suppress tangents.
5. Restate state every turn.
6. Specific time estimates (minutes, not "a bit").
7. Make wins visible.
8. Matter-of-fact errors.
9. Cap lists at 5 items.
10. No preamble. No recap. No closers.

## Tune it

Edit `skills/accessible-output/SKILL.md`. Re-invoke `/accessible-output` in Claude Code or `$accessible-output` in Codex.

### Modes

The default mode is `both`. Select one explicitly when the response should target a single set of needs:

- `adhd`: reduce working-memory load and starting friction.
- `autistic`: reduce ambiguity and make structure, assumptions, and timing explicit.
- `both`: combine both accommodations.

Examples: `/accessible-output adhd` or `$accessible-output autistic`.

## Credits

Loosely based on *The Adult ADHD Tool Kit* by J. Russell Ramsay and Anthony L. Rostain. Adapted for how an LLM should respond, not how a human should organize their day.

## License

MIT.

Star ⭐ if it saved you one scroll past one "Great question!"
