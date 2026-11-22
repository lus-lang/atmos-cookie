# AGENTS.md

`lus-lang/atmos-cookie` is the repository of the `cookie` package of the atmosphere registry. Programs load the package with `require("https://atmosp.here/2.0/cookie.lus")`.

## Scope

`cookie` parses, formats, and signs HTTP cookies. Its plugin gives `web` applications parsed request cookies and reply methods that set and clear cookies. The public API is every function that `cookie.lus` returns in its module table. A change to that API needs a new entry in `CHANGELOG.md` and a version change in the header.

## Layout

- `cookie.lus` is the whole package. Its header doc comment contains the package metadata and the declared permissions.
- `tests/*_test.lus` are the tests. They load `cookie.lus` from the parent of `TEST_DIR`, the directory that holds the test file.

## Dependencies

- `web`, for the plugin only
- the standard library `crypto` module, for signing only

The tests load `web` from a checkout of `lus-lang/atmos-web` next to this repository, so clone it into the same parent directory first.

## Commands

Run these commands from the root of the repository.

```sh
lus test tests          # run the tests
lus check cookie.lus     # lint
lus doc cookie.lus       # print the reference
```

## Rules

- Every public function has a doc comment that states each result and each error, following `spec/design/style.md` of the Lus repository.
- The package never calls `pledge`. A new permission is declared in the header and in the README.
- Prose follows the `lus-writing` skill, which `lus agents init` installs and https://lus.dev/agents/skills/lus-writing/SKILL.md serves. In particular, prose has no dashes or semicolons and never names the Roblox Lua dialect.
- Every bug fix comes with a test that fails without it.
