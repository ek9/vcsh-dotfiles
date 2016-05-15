vcsh-dotfiles
=============

[vcsh-dotfiles][0] aims to simplify the bootstrap procedure of managing your
dotfiles with [vcsh][1].. It sets up [vcsh][1], [mr][2], adds usable hooks and
lays down simple directory that [vcsh repos][#vcsh repositories] can follow.
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

Run `vcsh-dotfiles install` via this one-liner:

    $ curl https://raw.githubusercontent.com/ek9/vcsh-dotfiles/master/.local/bin/vcsh-dotfiles | bash -s install

Most vcsh repositories should be compatible with this format as it follow
standard [vcsh][1] and [mr][2] configuration.

## Usage

`vcsh-dotfiles` supports the following commands:

- `install` - used to install vcsh, mr and bootstrap vcsh-dotfiles.
- `verify` - used to verify existing `vcsh-dotfiles` setup.
- `help` - show help

Examples:

    $ vcsh-dotfiles verify
    $ vcsh-dotfiles help

## vcsh repositories

Related vcsh repositories:

- [ek9/shell-config][10] - bash, zsh and tmux dotfiles.
- [ek9/vim-config][11] - vim

## Authors

Copyright (c) 2016 ek9 <dev@ek9.co> (https://ek9.co).

Copyright (c) 2011-2015 Vincent Demeester for portions of code from
[vdemeester/vcsh-home][3] project.

## License

TBA

[0]: https://github.com/ek9/vcsh-dotfiles
[1]: https://github.com/RichiH/vcsh
[2]: https://github.com/joeyh/myrepos
[3]: https://github.com/vdemeester/vcsh-home
[10]: https://github.com/ek9/shell-config
[11]: https://github.com/ek9/vim-config
