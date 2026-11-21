# Changelog

## 0.1.0

The first prototype of `cookie`, written against the Lus 2.0 runtime on the `rewrite` branch.

Signing uses the final `crypto.hmac`, which returns a vector. A test checks that two cookies reach the client as two `Set-Cookie` lines.
