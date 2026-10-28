---
"just-bash": patch
---

Preserve prepared output destinations when commands change directories and apply output, read-write (`<>`), and input-only redirects in source order. Combined redirects to `/dev/stdout` and `/dev/stderr` use the selected stream, input redirects on stdout or stderr leave stdin unchanged, and duplicated read-write destinations retain both stdout and stderr output.
