# Doom Emacs prebuilt release

This public repository publishes the Linux x86_64 prebuilt Doom Emacs package used by `linux-setup` V2.

## Current release

- Doom master: `e545441ca954a0c43118f98c050ae77dd8d4818e` (`2.2.4`)
- Doom modules submodule: `d57ab52a3425b6d39564fb011b0e9571da0e270f`
- Build Emacs: GNU Emacs `30.2` (`/usr/bin/emacs`)
- Straight repositories: `203`
- Compiled Straight build directories: `188` (`.local/straight/build-30.2`)
- Generated profile: `.local/etc/@/init.30.2.el`
- Asset: `doom-emacs-prebuilt.tar.zst`
- Asset size: `211635723` bytes
- Asset SHA-256: `6233be38e1b299d0b1a13872843c33ce12173b3789a6c55465a19931d12858b0`

All bundled Git repositories are one-commit shallow snapshots at their pinned HEADs; full history is deliberately excluded. The archive also contains the current Doom configuration and its small bootstrap dependency set. It deliberately excludes Doom envvars, Emacs cache/state, native eln cache, browser profiles, authinfo, keys, and temporary runtime files.

## ABI boundary

This is a prebuilt Linux x86_64 artifact, not a source-only Doom bundle. Its bundled build tree was produced with GNU Emacs 30.2 and the local Linux toolchain. The target must provide a compatible x86_64 userspace/libc and the configuration's external programs. After extraction V2 runs the bundled Doom locally with `sync --reload --no-env`, rebuilding the profile for the target's actual Emacs version without fetching package history.

The source and Straight repositories remain in the archive for inspection/reproducibility, but their presence does not make byte-compiled output ABI-independent.
