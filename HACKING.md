# venenux repositories for stable releases

PLEAE READ [README.md](README.md), this is a VenenuX repositories for first generation of modern computers, 
means its for 32bit and 64bit systems and not so older Debian's/VenenuX's, mostly, Debian 10, Debian 11 and Debian 12.

**Do you want more modern ones? theck http://venenux.github.io/venenuxdebs4/ repository for next Debian !**

## Supported Debians

* Debian 10 buster and with this support limited to winbuntu 19.04, **likely VenenuX Debian 10**
* Debian 11 bullseye and with this support limited to winbuntu 20.04, **likely VenenuX Debian 11**
* Debian 12 bookworm and with this support limited to winbuntu 22.04, **likely VenenuX Debian 12**

## How CONTRIBUTE to this repository

You can fill an issue on Codeberg, or use Telegram Venenux groups:

* https://codeberg.org/venenux/venenux/issues
* https://t.me/latam_debian (Debian only spanish)
* https://t.me/open_debian_devuan (Debian and/or Devuan english also other langs)
* https://t.me/venenux (English and Spanish also)

#### addiding packages

We just manually put packages compiled already on OBS open suse build service.
The structure just follows the debian repository structure.
The package must be compiled agains vanilla debian versions of agains our repo packages, 
for that you can use (by sending a task/proposal) on OBS 
place at https://build.opensuse.org/project/subprojects/home:venenux for older 
debians or at https://build.opensuse.org/project/subprojects/home:vengnuli

#### regenerate index packages

after cloning the repo just get into the directory and then run in root repository:
`for dist in any buster bullseye bookworm; do for ar in i386 amd64; do dpkg-scanpackages -a $ar -m $dist > dists/$dist/main/binary-$ar/Packages; done; done`
and later you can generate the index compresed with
`for dist in any buster bullseye bookworm; do for ar in i386 amd64; do gzip -c dists/$dist/main/binary-$ar/Packages > dists/$dist/main/binary-$ar/Packages.gz; done; done`

This is basically for each distro (wheezy, jessie stretch) do a dpkg-scanpackages toa specific architecture, 
by example for i386 packages over wheezy index will be :
`dpkg-scanpackages -a i386 -m buster > dists/buster/main/binary-i386/Packages`
and later compreses with :
`gzip -c dists/buster/main/binary-i386/Packages > dists/buster/main/binary-i386/Packages.gz`

This repository only provide few 32bit i386 and much more 64bit amd64 packages for modified computers!
