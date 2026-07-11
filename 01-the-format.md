# The format

A Conventional Commit message has a structured first line, then an optional body and optional footers, each separated by a blank line. The first line is the only required part, and it carries the type, an optional scope, and a short description.

## The anatomy

```
<type>[optional scope]: <description>
[blank line]
[optional body]
[blank line]
[optional footer(s)]
```

The first line is the subject. The type says what kind of change this is (for example `feat` or `fix`). The optional scope names the part of the codebase affected and goes in parentheses right after the type. The description is a short summary of the change.

## A full example

```
feat(auth): add password reset via email

Users can now request a reset link from the login page. The
link expires after 30 minutes and is single use. This closes a
long-standing gap where locked-out users had to contact support.

Refs: #218
```

Here `feat` is the type, `auth` is the scope, and the text after the colon is the description. The body explains the why in plain sentences. The footer references an issue.

## Rules for the first line

The description is written in the imperative mood, as if giving a command: "add password reset", not "added" or "adds". By convention it starts lowercase and has no trailing period. Keep it short and specific.

The scope is always optional. A commit with no scope is perfectly valid:

```
fix: prevent crash when config file is missing
```

Note the colon and single space after the type or scope. That separator is required, and tooling relies on it to parse the message.
