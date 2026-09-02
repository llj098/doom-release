# Doom Emacs prebuilt release

This private repository publishes the Linux x86_64 prebuilt Doom Emacs package used by `linux-setup` V2.

## Current release

- Doom master: `e545441ca954a0c43118f98c050ae77dd8d4818e` (`2.2.4`)
- Doom modules submodule: `d57ab52a3425b6d39564fb011b0e9571da0e270f`
- Build Emacs: GNU Emacs `30.2` (`/usr/bin/emacs`)
- Straight repositories: `203`
- Compiled Straight build directories: `188` (`.local/straight/build-30.2`)
- Generated profile: `.local/etc/@/init.30.2.el`
- Asset: `doom-emacs-prebuilt.tar.zst`
- Asset size: `634155490` bytes
- Asset SHA-256: `ce73cb1de10cd4a9b03da93d88e0f9f7e1a4ea5f34efe7f86c4e3acc703d1ed2`

The archive also contains the current Doom configuration and its small bootstrap dependency set. It deliberately excludes Doom envvars, Emacs cache/state, native eln cache, browser profiles, authinfo, keys, and temporary runtime files.

## ABI boundary

This is a prebuilt Linux x86_64 artifact, not a source-only Doom bundle. Its `.elc` files and any compiled native modules are built/tested with GNU Emacs 30.2 and the local Linux toolchain. V2 therefore reads `emacs --version` on the target and rejects a version mismatch; it does not silently fetch or rebuild the 203 repositories. The target must also provide a compatible x86_64 userspace/libc and the external programs required by the configuration. After extraction V2 runs Doom's local `sync --reload --no-env` only to regenerate absolute profile paths for the target home; this operation does not fetch packages.

The source and Straight repositories remain in the archive for inspection/reproducibility, but their presence does not make byte-compiled output ABI-independent.
