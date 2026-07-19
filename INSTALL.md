# Install accessible-output

A Claude Code and Codex plugin. One skill inside.

## Claude Code

```bash
claude plugin marketplace add advatar/accessible-output
claude plugin install accessible-output@accessible-output
```

Open Claude Code, type `/accessible-output`. Add `adhd`, `autistic`, or `both` to select a mode.

To disable: `claude plugin disable accessible-output` (or `/plugin disable accessible-output` from within Claude Code). Re-enable later with `enable` instead of `disable`.

## Verify

```bash
claude plugin list
```

Look for `accessible-output  (enabled)`.

## Codex

```bash
codex plugin marketplace add advatar/accessible-output
codex plugin add accessible-output@accessible-output
```

Start a new Codex thread and invoke `$accessible-output`. Add `adhd`, `autistic`, or `both` to select a mode. Codex may also activate the skill automatically because it applies to every response.

Verify with:

```bash
codex plugin list
```

## Update

```bash
claude plugin marketplace update accessible-output
codex plugin marketplace upgrade accessible-output
```

Start a new Claude Code or Codex session after updating.

## Uninstall

```bash
claude plugin uninstall accessible-output
claude plugin marketplace remove accessible-output
codex plugin remove accessible-output
codex plugin marketplace remove accessible-output
```

## Always-on (optional)

To skip `/accessible-output` and apply the rules from message one, add to `~/.claude/CLAUDE.md`:

```markdown
## Output style

Always follow the rules in the `accessible-output` skill: action-first, numbered steps, no preamble, no closers, state restated each turn.
```

## Troubleshooting

**The skill is missing from autocomplete.** Restart Claude Code or Codex. Plugin and skill changes are picked up in a new session.

**Marketplace installation fails.** Use `advatar/accessible-output` exactly. For local development, point either CLI at the cloned repo root, not `.claude-plugin/`.

**Skill activates but model still preambles.** Open a new session. Old context may carry. If it still drifts, tighten the rule wording in `skills/accessible-output/SKILL.md`, then re-invoke.

**Want different rules.** Edit `skills/accessible-output/SKILL.md`. Re-invoke `/accessible-output` in Claude Code or `$accessible-output` in Codex (or restart) and the new rules apply.
