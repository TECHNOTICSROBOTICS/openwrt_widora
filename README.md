## How to compile?
# 1.install depend
## Ubuntu14.04
$ sudo apt-get update

$ sudo apt-get install git g++ make libncurses5-dev subversion libssl-dev gawk libxml-parser-perl unzip wget python xz-utils vim
## Macos
note: install brew and Xcode command line tools

$brew install coreutils findutils gawk gnu-getopt gnu-tar grep wget quilt xz

note: gnu-getopt is keg-only, so force linking it:brew ln gnu-getopt --force

# 2.download the source use git
$ git clone https://github.com/widora/openwrt_widora.git
# 3.update the feeds
$ cd openwrt_widora
$ ./scripts/feeds update -a

$ ./scripts/feeds install -a
# 4.config
$ make menuconfig
select the target:

Target System(Ralink RT288x/RT3xxx) --->

Subtarget(MT7688 based board) --->

Target Profile(Widora) --->

# 5.make
$ make -j4
# 6.image
the binary image name like this in bin/ramips/:
openwrt-ramips-mt7688-Widora-squashfs-sysupgrade.bin
