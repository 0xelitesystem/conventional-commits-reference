# Good practices

Good Conventional Commits are small, clearly worded, and honest about scope, so the history reads like a log of decisions rather than a pile of noise. Here are practical rules that hold up in real projects.

## One logical change per commit

Keep each commit focused on a single change. If you fixed a bug and also renamed some files, that is two commits. Small, single-purpose commits make review, revert, and changelog grouping all cleaner.

## Write the description as a command

Use the imperative present tense in the description: "add", "fix", "remove", not "added" or "fixes". Read it as "this commit will ...". Keep the subject short, around 50 characters, so it stays readable in logs and tooling.

```
fix: handle null user in session lookup
```

## Use the body for why, not what

The diff already shows what changed. Use the body to explain why the change was needed, what you ruled out, and anything a future reader would want to know. Wrap the body at a comfortable width and separate it from the subject with a blank line.

## Reference issues in footers

Link related tickets in footers so the history connects to your tracker:

```
fix: reject expired tokens

Refs: #123
Closes: #45
```

## Remember what affects versioning

Only `feat`, `fix`, and breaking changes move the version number. Types like `docs`, `style`, `refactor`, `test`, `chore`, `ci`, and `build` are informational: they keep the history tidy and shape the changelog, but they do not trigger a semver bump on their own.

## Enforce it automatically

You do not have to police this by hand. A commit-lint hook can check every message against the convention before it lands, rejecting a commit that has an unknown type or a malformed subject. Wiring that into a pre-commit or commit-msg hook keeps the whole team consistent without anyone having to remember the rules.
