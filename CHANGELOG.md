# Changelog

## 1.0.0

**Release date:** TBD

Version 1.0.0 is the first release of `cookie`.

- Added the `cookie` package.
  - `cookie.parse`: Parses the value of a `Cookie` header into a table from names to values.
  - `cookie.format`: Formats the value of a `Set-Cookie` header with its attributes.
  - `cookie.sign`: Signs a value with HMAC-SHA-256.
  - `cookie.unsign`: Checks a signed value and returns the original value.
  - `cookie.register`: Registers the cookie plugin on a `web` scope, which adds `req.cookies` and the reply methods `cookie` and `clear_cookie`.
