# Install i-have-adhd

A Claude Code and Codex plugin. One skill inside.

## Claude Code

```bash
claude plugin marketplace add ayghri/i-have-adhd
claude plugin install i-have-adhd@i-have-adhd
```

Open Claude Code, type `/i-have-adhd`.

To disable: `claude plugin disable i-have-adhd` (or `/plugin disable i-have-adhd` from within Claude Code). Re-enable later with `enable` instead of `disable`.

## Verify

```bash
claude plugin list
```

Look for `i-have-adhd  (enabled)`.

## Codex

```bash
codex plugin marketplace add ayghri/i-have-adhd
codex plugin add i-have-adhd@i-have-adhd
```

Start a new Codex thread and invoke `$i-have-adhd`. Codex may also activate the skill automatically because it applies to every response.

Verify with:

```bash
codex plugin list
```

## Update

```bash
claude plugin marketplace update i-have-adhd
codex plugin marketplace upgrade i-have-adhd
```

Start a new Claude Code or Codex session after updating.

## Uninstall

```bash
claude plugin uninstall i-have-adhd
claude plugin marketplace remove i-have-adhd
codex plugin remove i-have-adhd
codex plugin marketplace remove i-have-adhd
```

## Always-on (optional)

To skip `/i-have-adhd` and apply the rules from message one, add to `~/.claude/CLAUDE.md`:

```markdown
## Output style

Always follow the rules in the `i-have-adhd` skill: action-first, numbered steps, no preamble, no closers, state restated each turn.
```

## Troubleshooting

**The skill is missing from autocomplete.** Restart Claude Code or Codex. Plugin and skill changes are picked up in a new session.

**Marketplace installation fails.** Use `ayghri/i-have-adhd` exactly. For local development, point either CLI at the cloned repo root, not `.claude-plugin/`.

**Skill activates but model still preambles.** Open a new session. Old context may carry. If it still drifts, tighten the rule wording in `skills/i-have-adhd/SKILL.md`, then re-invoke.

**Want different rules.** Edit `skills/i-have-adhd/SKILL.md`. Re-invoke `/i-have-adhd` in Claude Code or `$i-have-adhd` in Codex (or restart) and the new rules apply.
