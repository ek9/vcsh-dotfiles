vcsh-dotfiles
=============

[vcsh-dotfiles][0] is a generic script which aims to simply managing your
dotfiles by setting up useful hooks for [vcsh][1] and configuring [mr][2] to be
extendable. This is done by laying down a basic structure that [vcsh][1]
compatible repositories can then utilize. It is inspired by the bootstrap
script in [vdemeester/vcsh-home][3] project.

## Overview

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
    - `.config/mr/config.d` (for single [vcsh][1] repositories)
    - `.config/mr/groups.d` (for groups - dependencies and [vcsh][1]
      repository)).
  This allows any repositories to extend `mr` configuration further.

## Requirements

- `curl` or `wget`
- `git`

## Install

Install `vcsh-dotfiles` and run it to bootstrap itself:

    $ curl https://raw.githubusercontent.com/ek9/vcsh-dotfiles/.local/bin/vcsh-dotfiles | bash

Most vcsh repositories should be compatible with this format. Examples:

- [ek9/shell-config][10]
- [ek9/vim-config][11]

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
