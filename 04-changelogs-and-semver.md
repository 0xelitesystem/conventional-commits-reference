# Changelogs and semver

The real payoff of Conventional Commits is automation: because every commit is labeled, tools can read the history and both build a changelog and pick the next version number without human sorting. This file explains the two mappings that make that work.

## Generating changelogs

Release tools parse the type of each commit since the last release and group them into changelog sections. A typical generated changelog has headings like Features (from `feat` commits), Bug Fixes (from `fix` commits), and Performance Improvements (from `perf` commits), with each commit description listed under the right heading. Breaking changes get their own prominent section built from the `BREAKING CHANGE` footers or `!` markers. Commits of purely internal types like `chore` or `ci` are usually left out of the public changelog.

## Deciding the version bump

The convention maps commit types onto Semantic Versioning, which uses MAJOR.MINOR.PATCH. The mapping is:

- a `fix` commit produces a PATCH bump (for example 1.4.2 becomes 1.4.3).
- a `feat` commit produces a MINOR bump (for example 1.4.2 becomes 1.5.0).
- any commit marked with `BREAKING CHANGE` or `!` produces a MAJOR bump (for example 1.4.2 becomes 2.0.0), regardless of its type.

When a release contains a mix, the highest applicable bump wins. A release with several fixes and one feature bumps the MINOR. A release with any breaking change bumps the MAJOR even if everything else is a fix.

## The result: automated releases

Put those two mappings together and a release tool can, on merge to the main branch, compute the next version, tag it, write the changelog, and publish, all from commit messages alone. That is why teams adopt the convention: consistent commit text turns into a reliable, hands-off release pipeline.
