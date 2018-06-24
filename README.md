== setup

=== download original kernel sources to reduce upload size:

wget https://launchpad.net/ubuntu/+archive/primary/+files/linux_3.13.0.orig.tar.gz
wget https://launchpad.net/ubuntu/+archive/primary/+files/linux_4.4.0.orig.tar.gz
wget https://launchpad.net/ubuntu/+archive/primary/+files/linux_4.13.0.orig.tar.gz
wget https://launchpad.net/ubuntu/+archive/primary/+files/linux_4.15.0.orig.tar.gz

=== setup git repositories:

- in folder tuxonice-ppa-scripts:
origin  git@github.com:mschlaeffer/tuxonice-ppa-scripts.git (fetch)

- in folder linux:
github  git@github.com:mschlaeffer/ubuntu-kernel-with-tuxonice.git
lp      git+ssh://mschlaeffer@git.launchpad.net/~tuxonice/linux
toi     git://github.com/NigelCunningham/tuxonice-kernel.git
linux   git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
stable  git://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
trusty  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux/+git/trusty
xenial  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux/+git/xenial
artful  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux/+git/artful
bionic  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux/+git/bionic

- in folder linux-meta:
trusty  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux-meta/+git/trusty
xenial  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux-meta/+git/xenial
artful  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux-meta/+git/artful
bionic  git://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux-meta/+git/bionic

== build

- add tuxonice-ppa-scripts to your $PATH

- build linux-image:
ppa-linux-tuxonice xenial 4.4.0 83 106 1 ppa:tuxonice/staging

- build linux-meta:
ppa-linux-meta-tuxonice xenial 83 89 1 ppa:tuxonice/staging

- rebuild all packages with newer versions available:
ppa-rebuild-linux

