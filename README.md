# cookie

`cookie` parses, formats, and signs HTTP cookies. Its plugin gives `web` applications parsed request cookies and reply methods that set and clear cookies.

The following example sets and reads the cookies that store the color theme and the language of a visitor.

```lus nocheck
local cookie = require("https://atmosp.here/2.0/cookie.lus")

print(cookie.format("theme", "dark", { max_age = 3600, http_only = true }))
--> theme=dark; Max-Age=3600; HttpOnly
print(cookie.parse("theme=dark; lang=fr").lang)   --> fr
```

The package requires Lus 2.0 and declares no permissions. It never calls `pledge`, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `cookie.lus`, which `lus doc cookie.lus` prints.
