# Common types

The type is the first token of a Conventional Commit and it labels the kind of change. The spec only mandates `feat` and `fix`, but a widely used set of additional types has become standard practice. Here is each one with its meaning and an example.

## The standard types

- `feat` a new feature for the user.
  ```
  feat: add dark mode toggle
  ```

- `fix` a bug fix.
  ```
  fix: correct total when cart is empty
  ```

- `docs` documentation only changes.
  ```
  docs: update install steps
  ```

- `style` formatting and whitespace that does not change code meaning.
  ```
  style: reformat with prettier
  ```

- `refactor` a code change that neither fixes a bug nor adds a feature.
  ```
  refactor: extract validation into helper
  ```

- `perf` a change that improves performance.
  ```
  perf: cache lookup results
  ```

- `test` adding or correcting tests.
  ```
  test: cover empty input case
  ```

- `build` changes to the build system or external dependencies.
  ```
  build: bump webpack to 5.90
  ```

- `ci` changes to CI configuration and scripts.
  ```
  ci: run tests on node 20
  ```

- `chore` other maintenance that does not touch source or tests.
  ```
  chore: update license year
  ```

- `revert` reverts a previous commit.
  ```
  revert: undo feat that broke login
  ```

## Which ones matter for versioning

Only `feat` and `fix` (and any breaking change) affect the version number under Semantic Versioning. The rest are informational: they make the history readable and help group changelog entries, but they do not bump the version on their own.
