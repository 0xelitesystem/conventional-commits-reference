# Breaking changes

A breaking change is a change that forces users of your code to update how they use it, and the spec gives you two ways to mark one. You can add a `!` before the colon on the first line, or add a `BREAKING CHANGE:` footer, or both.

## Way one: the exclamation mark

Put a `!` immediately after the type or scope, right before the colon:

```
feat(api)!: remove deprecated endpoint
```

The `!` is a quick visual signal on the subject line that this commit breaks compatibility. It works with a scope or without one:

```
refactor!: drop support for node 14
```

## Way two: the footer

Add a footer that begins with `BREAKING CHANGE:` followed by a description of what broke and how to migrate:

```
feat: send config as json

BREAKING CHANGE: the config file is now json instead of yaml.
Rename config.yaml to config.json and convert the contents.
```

The token `BREAKING CHANGE` must be uppercase in the footer. The spec also allows the hyphenated form `BREAKING-CHANGE:` as an exact synonym, which is handy because footer tooling often prefers hyphenated keys.

## Using both together

You can combine the two for maximum clarity. The `!` flags it on the subject and the footer explains the migration:

```
feat(api)!: change auth header format

BREAKING CHANGE: clients must send Authorization: Bearer <token>
instead of the old X-Auth-Token header.
```

## Why it matters

A breaking change correlates to a MAJOR version bump under Semantic Versioning, regardless of the commit type. Whether the commit is a `feat`, a `fix`, or a `refactor`, marking it breaking is what raises the major version. This is the single most important signal in the whole convention, so mark breaks explicitly.
