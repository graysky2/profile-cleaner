# Profile-cleaner
Use profile-cleaner to reduce the size of browser profiles by organizing their sqlite databases using sqlite3's vacuum and reindex functions. The term "browser" is used loosely since profile-cleaner happily works on some email clients and newsreaders too.

## Supported Browsers
* Brave (stable, beta, dev and nightly) (https://aur.archlinux.org/packages/brave-bin)
* Chromium (stable, beta, and dev)
* Conkeror
* Edge
* Falkon
* Firefox (stable, beta, and aurora)
* Google-chrome (stable, beta, and dev)
* Heftig's version of Aurora (https://bbs.archlinux.org/viewtopic.php?id=117157)
* Icecat
* Icedove
* Inox (https://bbs.archlinux.org/viewtopic.php?id=198763)
* Midori
* Newsboat
* Palemoon
* Qupzilla
* Seamonkey
* Thunderbird
* Tor-browser
* Vivaldi (stable and snapshot)

## Documentation
Consult the man page.

## Installation from Source
To build from source, see the included INSTALL text document.

## Installation from Distro Packages
* ![logo](http://www.monitorix.org/imgs/archlinux.png "arch logo")Arch via the official package in [community]
* ![logo](http://i.imgur.com/ooVjgFG.png "gentoo logo")Gentoo: See instructions below
* ![logo](https://i.postimg.cc/13Jzxh5C/nix.png "nixos logo")NixOS: in the official repos
* ![logo](http://wiki.codeblocks.org/images/8/8b/Slackware-logo_32.png "slack logo")Slackware: on [slackbuilds](http://slackbuilds.org/apps/profile-cleaner/)

### Gentoo Users
Profile cleaner is in the main repo:

    emerge -av app-admin/profile-cleaner

### Other Distros
If you are interested in packaging profile-cleaner for your favorite distro, please contact me.

## Dependencies
* bash
* bc
* findutils
* sqlite
* parallel

## Sample Output and Results Using an "Uncleaned" Firefox Profile:

	Size before: 154.17 Mbytes
	Size after:  99.11 Mbytes

	$ profile-cleaner f

	/home/facade/.mozilla/firefox/zee52krz.default/cookies.sqlite reduced by .87 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/signons.sqlite reduced by .41 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/downloads.sqlite reduced by .56 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/chromeappsstore.sqlite reduced by .03 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/urlclassifier3.sqlite reduced by 43.10 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/formhistory.sqlite reduced by .11 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/addons.sqlite reduced by 0 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/permissions.sqlite reduced by 0 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/content-prefs.sqlite reduced by 0 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/extensions.sqlite reduced by 0 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/webappsstore.sqlite reduced by 0 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/OfflineCache/index.sqlite reduced by 0 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/search.sqlite reduced by 0 Mbytes
	/home/facade/.mozilla/firefox/zee52krz.default/places.sqlite reduced by 9.98 Mbytes

	firefox profile reduced by 55.06 Mbytes

## Speed Comparison
28-Nov-2012		Profile-cleaner has been rewritten to use GNU Parallel for processing.

Here is a contrived example cleaning 6 firefox profiles comparing the classical version of Profile-cleaner which used for loops to process profiles to the new version:

* There are a total of 312 M in the 6 "dirty" profiles.
* Test machine is an Intel 3770K @ 4.50 GHz.
* After cleaning there is a total of 213 M in the 6 "clean" profiles.

new 4.07s user 0.42s system 318% cpu 1.411 total

old 8.15s user 0.43s system 95% cpu 8.942 total

Your mileage may vary.
