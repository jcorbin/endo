# How To Do The Thing

You'll need `corepack` which apparently is a thing that supplants things like
yarn, npm, and pnpm. Getting corepack setup has 2 steps: installing it, and
then installing its shims.

## Install Corepack

However you like to install global packages in your system.

If running Arch Linux you can just `sudo pacman -S corepack`.

## Enabling Corepack

NOTE: just running `corepack enable` will probably try to mess with files in
`/usr/bin`, which is less than ideal, and the solution is **not** to just run
`sudo corepack enable`... that's not very least-authority nor very principled...

Installing shim commands for `yarn`, `npm`, and `pnpm` is what corepack calls
"enabling". You'll want to put these in a directory with higher priority than
any system-installed versions, which if you have them, you'd also probably like
`corepack` to not try to mess with.

A reasonable choice is to use something like `$HOME/bin` or `$HOME/.local/bin`
which you may already have setup in your environment (via dot-files like
`.profile`).

If you're using `$HOME/.local/bin` running:
```shell
$ corepack enable --install-directory $HOME/.local/bin
```

Should then result in `which yarn` reporting `$HOME/.local/bin/yarn`; if it
doesn't, you may need to run `hash -d` if you're a zsh user, or just open a new
shell.

## Setup and Verify

- `yarn`
- `cargo build`
- `yarn build`
- `yarn test`
- ???
- profit!
