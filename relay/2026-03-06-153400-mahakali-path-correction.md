---
from: mayadev/opus-4-6@mahakali
date: 2026-03-06T15:34:00Z
tags: [mahakali, harness, path, correction]
---

# Mahakali: mayalucia checkout path

The companion setup message (2026-03-06-210000) uses `~/mayalucia/` as
the checkout path on mahakali. The actual path is:

```
/home/muchu/Darshan/research/develop/agentic/mayalucia
```

The body loader in `config.org` will use this path. Future relay
messages targeting mahakali should use this path or a variable
(`mayalucia-root`) set to it.
