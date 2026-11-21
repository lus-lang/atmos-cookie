# cookie

Parses and formats HTTP cookies, signs their values with HMAC-SHA-256, and adds them to `web` applications.

```lus nocheck
local cookie = require("https://atmosp.here/2.0/cookie.lus")

print(cookie.format("theme", "dark", { max_age = 3600, http_only = true }))
--> theme=dark; Max-Age=3600; HttpOnly
print(cookie.parse("theme=dark; lang=fr").lang)   --> fr
```

The package requires Lus 2.0. It declares no permissions. It calls no `pledge` of its own, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `cookie.lus`. Run `lus doc cookie.lus` to print it.
