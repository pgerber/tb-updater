# Tor Browser Downloader by Whonix developers #

Automates download and verification of Tor Browser from The Tor Project's
website. Useful for initial installation of Tor Browser, clean
re-installations of Tor Browser and keeping newly created Qubes AppVMs
inherited from updated Qubes TemplateVMs can ship up to date versions of
Tor Browsers.

Incapable of preserving of updating and preserving user data. Use
Tor Browser's internal updater for that purpose. Notifies about already
exiting installations of Tor Browser. Renamed rather than deletes old versions
of Tor Browsers to avoid user data loss.

Has a cli and a gui mode. Can auto detect latest version numbers or use user
configured version numbers. Comes with a download confirmation screen that
lets users choose which version to download. [1] Has a installation
confirmation screen [2] that enables users to detect indefinite freeze and
rollback attacks.

Integrates well with tb-starter, tb-default-browser and
open-link-confirmation package as well as with Qubes.

Without the curl-scripts package installed, the GUI will not move the progress
bar.

If you have the curl-scripts package installed, it will show a nicer progress
bar when run in terminal and more meaningful curl exit code messages, when
curl failed.

When having the anon-shared-helper-scripts package installed (recommended for
Anonymity Distributions), Tor Browser Downloader will check, that Tor is
enabled,  that no package manager is currently running and that Tor finished
bootstrapping before download attempts.

This package is produced independently of, and carries no guarantee from,
The Tor Project.

[1] https://www.whonix.org/wiki/Tor_Browser#Download_Confirmation_Screen
[2] https://www.whonix.org/wiki/Tor_Browser#Installation_Confirmation_Screen

(This package description has been [automatically](https://github.com/Whonix/whonix-developer-meta-files/blob/master/debug-steps/packaging-helper-script) extracted and mirrored from `debian/control`.)

# Manual Page #

See also `man` folder for more information.

# Generic Readme #
## Readme Version ##

[Generic Readme](https://github.com/Whonix/whonix-developer-meta-files/blob/master/README_generic.md) Version 0.3

## Cooperating Anonymity Distributions ##

[Generic Readme](https://github.com/Whonix/whonix-developer-meta-files/blob/master/README_generic.md) beings here. Have a look into the `man` sub folder (if available).

The functionality of this package was once exclusively available in the [Whonix](https://www.whonix.org) ([github](https://github.com/Whonix/Whonix)) anonymity distribution.

Because multiple projects and individuals stated interest in various of Whonix's functionality (examples: [Qubes OS](http://qubes-os.org/trac) ([discussion](https://groups.google.com/forum/#!topic/qubes-devel/jxr89--oGs0)); [piratelinux](https://github.com/piratelinux) ([discussion](https://github.com/adrelanos/VPN-Firewall/commit/6147f0e606377f5a801e98daf22e24ba2c750a21#commitcomment-6360713))), it's best to share as much source code as possible, it's best to share certain characteristics [(such as /etc/hostname etc.) among all anonymity distributions](https://mailman.boum.org/pipermail/tails-dev/2013-January/002457.html)) Whonix has been split into [multiple separate packages](https://github.com/Whonix).

## Generic Packaging ##

Files in `etc/...` in root source folder will be installed to `/etc/...`, files in `usr/...` will be installed to `/usr/...` and so forth. This should make renaming, moving files around, packaging, etc. very simple. Packaging of most packages looks very similar.

## How to use outside of Debian or derivatives ##

Although probably due to generic packaging not very hard. Still, this requires developer skills. [Ports](https://en.wikipedia.org/wiki/Porting) welcome!

## How to Build deb Package ##

See comments below and [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

* Replace `apparmor-profile-torbrowser` with the actual name of this package (equals the root source folder name of this package after you git cloned it).
* You only need [config-package-dev](https://packages.debian.org/wheezy/config-package-dev), when it is listed in the `Build-Depends:` field in `debian/control`.
* Many packages do not have signed git tags yet. You may request them if desired.
* We might later use a [documentation template](https://www.whonix.org/wiki/Template:Build_Documentation_Build_Package).

## How to install in Debian using apt-get ##

Binary packages are available in Whonix's APT repository. By no means you are required to use the binary version of this package. This might be interesting for users of Debian and derivatives. **Note, that usage of this package outside of Whonix is untested and there is no maintainer that supports this use case.**

1\. Get [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

2\. Add Whonix's Signing Key to apt-key.

```
gpg --export 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA | sudo apt-key add -
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org stretch main" > /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install this package. Replace `package-name` with the actual name of this package.

```
sudo apt-get install package-name
```

## Cooperation ##

Most welcome. [Ports](https://en.wikipedia.org/wiki/Porting), distribution maintainers, developers, patches, forks, testers, comments, etc. all welcome.

## Contact ##

* Professional Support: https://www.whonix.org/wiki/Support#Professional_Support
* Free Forum Support: https://www.whonix.org/forum
* Github Issues
* twitter: https://twitter.com/Whonix

## Donate ##

* [Donate](https://www.whonix.org/wiki/Donate)
