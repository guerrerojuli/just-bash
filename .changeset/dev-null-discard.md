---
"just-bash": patch
---

Treat `/dev/null` redirects as a discard/EOF device without requiring filesystem device nodes. Output redirects discard data, input redirects return EOF, and read-write redirects support both behaviors. This works on filesystems that cannot initialize `/dev`, preserves command exit statuses, and prevents append redirects from growing a backing file.

This change covers redirect operators only. Commands that access `/dev/null` by path, such as `cat`, `cp`, and `test -e`, still depend on filesystem entries. `/dev/stdout` and `/dev/stderr` retain their existing behavior; stream-device identity and offset handling are separate work.
