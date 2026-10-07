# peetzweg/muvm: downstream fixes for omarchy-mac

This fork carries fixes to [AsahiLinux/muvm](https://github.com/AsahiLinux/muvm) that we run on omarchy-mac (Asahi Linux, M1 Pro) while they aren't upstream. They were written with AI assistance, which AsahiLinux's contribution policy doesn't accept, so they're kept here and rebased onto upstream regularly. Anyone is welcome to use them as a reference for a contributor-written fix.

| Branch | What |
|---|---|
| `relaunch-race` | launch: retry against a booting or exiting VM, and take over its lock ("could not connect to muvm server: Connection refused" when Steam is restarted quickly) |
| `env-hidpi` | env: pass through `GDK_SCALE`, `XCURSOR_SIZE`, `XCURSOR_THEME` |
| `passt-fd-leak` | net: don't keep passt's end of the socket pair open |
| `omarchy-mac` | upstream `main` + all of the above; what we build and run |

`sync` (this branch) only holds the workflow: weekly it rebases each fix branch onto upstream `main`, rebuilds `omarchy-mac`, checks that it compiles, and opens an issue if a rebase conflicts.
