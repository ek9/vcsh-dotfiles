vcsh-dotfiles
=============

[vcsh-dotfiles][0] aims to simplify the bootstrap procedure of managing your
dotfiles with [vcsh][1].. It sets up [vcsh][1], [mr][2], adds usable hooks and
lays down simple directory that [vcsh repos](#vcsh repositories) can follow.
It is inspired by the bootstrap script in [vdemeester/vcsh-home][3] repository.

## Features

- Automatically download and setup `vcsh` and `mr` by fetching files via
  curl/wget and git.
- Sets up `.local/bin` for local binaries and shell scripts (added to `PATH`)
- [vcsh][1] hooks setup to:
    - Enable sparse checkout.
    - Ignore `README`, `LICENSE` and other common development files.
    - Make backup copies of files that would be overwritten when cloning.
    - Repositories can have `.gitignore` files stored
      in `.gitignore.d/<repo-name>` of every repository
- [mr][2] `.mrconfig` setup to source files in:
    - `.config/mr/config.d` (for [vcsh][1] repositories)
  This allows any repositories to extend `mr` configuration further.

## Requirements

- `curl` or `wget`
- `git`

## Install

Run `vcsh-dotfiles bootstrap` via this `curl` one-liner:

    $ curl https://raw.githubusercontent.com/ek9/vcsh-dotfiles/master/.local/bin/vcsh-dotfiles | bash -s bootstrap

Source `~/.profile` to make sure `PATH` is updated:

    $ source ~/.profile

Run `mr update` to verify the boostrap:

    $ mr update

Most vcsh repositories should be compatible with this format as it follow
standard [vcsh][1] and [mr][2] configuration.

## Usage

You can use `vcsh-dotfiles` to clone vcsh repositories:

    $ vcsh-dotfiles clone https://github.com/ek9/shell-config

`vcsh-dotfiles` supports the following commands:

- `bootstrap` - used to bootstrap vcsh, mr and bootstrap vcsh-dotfiles.
- `clone` - used to clone vcsh repositories. Run `mr update` at the end. Will
   not try to clone already cloned repository and will only run `mr update`.
- `verify` - used to verify existing `vcsh-dotfiles` setup.
- `help` - show help

Examples:

    $ vcsh-dotfiles clone https://github.com/ek9/shell-config
    $ vcsh-dotfiles verify
    $ vcsh-dotfiles help

You can check [ek9/dotfiles][10] for various repositories that use
[vcsh-dotfiles][0].

## Authors

Copyright (c) 2016 ek9 <dev@ek9.co> (https://ek9.co).

Copyright (c) 2011-2015 Vincent Demeester for portions of code from
[vdemeester/vcsh-home][3] project.

## License

TBA.

[0]: https://github.com/ek9/vcsh-dotfiles
[1]: https://github.com/RichiH/vcsh
[2]: https://github.com/joeyh/myrepos
[3]: https://github.com/vdemeester/vcsh-home
[10]: https://github.com/ek9/dotfiles
