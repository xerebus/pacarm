pacarm
======

Bash script to fetch outdated Arch Linux packages from the Arch Rollback Machine automatically

Usage
-----

	pacarm -S <pkgname>

What It Does
------------

`pacarm` will run `pacman -S --noconfirm <pkgname>` and collect the output in a file. It will then search this output for 404 errors, indicating old packages that have been replaced by newer versions in the Arch repositories. `pacarm` will then use xyne's `armh` script to find these outdated packages from the Arch Rollback machine at http://arm.konnichi.com/, download them, and install them.

Disclaimers
-----------

1. This script is quickly written, inefficient, and probably unsafe. Use at your own risk.
2. It depends heavily on searching output (lots of `grep`ing and `cut`ing), so if `pacman` or `armh` change the way their output is formatted, this script will break.
3. This allows you to install *outdated* packages. *DO NOT* report bugs for packages if you use `pacarm` as the versions of the packages you're using will probably be unsupported.
