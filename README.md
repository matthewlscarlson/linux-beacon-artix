# linux-beacon-artix
Patched Artix/Arch kernel that fixes iwlwifi driver

The patch is basically [mikezackles's](https://github.com/mikezackles/linux-beacon-pkgbuild). It fixes a stupid bug whereby `iwlwifi` frequently disconnects and says, 'No beacon heard and the time event is over already'. It's been three years, yet the bug persists: [https://bugzilla.kernel.org/show_bug.cgi?id=203709](https://bugzilla.kernel.org/show_bug.cgi?id=203709).

But that repository is not always updated, so I created my own to be updated at my discretion. It uses the namesake of Artix, but Arch and Artix use virtually (or even exactly) the same kernel, as far as I am aware.
