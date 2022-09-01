# linux-beacon-artix
Patched Artix/Arch kernel that fixes iwlwifi driver

The patch is basically [mikezackles's](https://github.com/mikezackles/linux-beacon-pkgbuild). It fixes a stupid bug whereby `iwlwifi` frequently disconnects and says, 'No beacon heard and the time event is over already'. It's been three years, yet the bug persists: [https://bugzilla.kernel.org/show_bug.cgi?id=203709](https://bugzilla.kernel.org/show_bug.cgi?id=203709).

But that repository is not always updated, so I created my own to be updated at my discretion. It uses the namesake of Artix, but Arch and Artix use virtually (or even exactly) the same kernel, as far as I am aware.

## Usage
First, create a file (e.g., in /etc/modprobe.d/wifi-fix.conf) containing this line:

```
options iwlwifi beacon_timeout=256
```

The number 256 is the number of beacons that must be missed before the driver disconnects.

Second, either tediously build the packages yourself or download prebuilt versions of them.

To install the prebuilt packages, navigate to [https://github.com/matthewlscarlson/linux-beacon-artix/releases](https://github.com/matthewlscarlson/linux-beacon-artix/releases) and download the two .pkg.tar.zst files associated with the most recent release.

**It would probably be a wise idea to back up your current kernel before proceeding.**

Third, open the terminal as the user `root` and run this command (with the dummy file names replaced by the actual file names) in the directory containing the downloaded files:

```shell
# pacman -U linux-beacon-headers-KERNEL_VERSION-x86_64.pkg.tar.zst linux-beacon-KERNEL_VERSION-x86_64.pkg.tar.zst
```
