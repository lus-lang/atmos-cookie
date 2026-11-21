# AGENTS.md

This repository, `lus-lang/atmos-cookie`, is the `cookie` package of the atmosphere registry. Programs load it with `require("https://atmosp.here/2.0/cookie.lus")`.

## Scope

Parses and formats HTTP cookies, signs their values with HMAC-SHA-256, and adds them to `web` applications. The public API is every function that `cookie.lus` returns in its module table. A change to that API needs a new entry in `CHANGELOG.md` and a version change in the header.

## Layout

- `cookie.lus` is the whole package. Its header doc comment carries the package metadata and the declared permissions.
- `tests/*_test.lus` are the tests. They load the package from the parent directory through `TEST_DIR`.

## Dependencies

- web (for the plugin only)
- the stdlib `crypto` module (for signing only)

The tests load `web` from a checkout of `lus-lang/atmos-web` next to this repository, so clone it into the same parent directory first.

## Commands

```sh
lus test tests          # run the tests
lus check cookie.lus     # lint
lus doc cookie.lus       # print the reference
```

## Rules

- Every public function has a doc comment that states each result and each error, following `spec/design/style.md` of the Lus repository.
- The package never calls `pledge`. A new permission is declared in the header and in the README.
- Prose has no dashes and no semicolons, and never names the Roblox Lua dialect.
- Every bug fix comes with a test that fails without it.
