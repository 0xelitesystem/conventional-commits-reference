# Conventional Commits

Conventional Commits is a lightweight convention for writing commit messages in a structured, machine-readable way. It defines a small set of rules for the first line of a commit so that both people and tooling can understand what changed. This reference explains the format in plain language with real example commit messages.

## The core idea

A Conventional Commit encodes the kind of change into the commit message itself, starting with a type like `feat` or `fix` followed by a colon and a short description. Because the format is predictable, automated tools can read your commit history to generate changelogs and decide the next version number without a human sorting through each commit. The convention is defined by the Conventional Commits 1.0.0 specification and pairs naturally with Semantic Versioning. The whole point is that a consistent commit message becomes structured data, not just a note to yourself.

## What is inside

- `01-the-format.md` the anatomy of a commit message and a full example.
- `02-common-types.md` the standard commit types with meanings and examples.
- `03-breaking-changes.md` the two ways to signal a breaking change.
- `04-changelogs-and-semver.md` how types map to changelogs and version bumps.
- `05-good-practices.md` practical rules for writing clean commits.

## The stance

This is a reference, not a lecture. It sticks to the 1.0.0 spec and shows literal syntax you can copy. If you only read one file, read `01-the-format.md`.

## License

MIT. Copyright 0xelitesystem 2026.
