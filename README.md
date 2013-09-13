# Profile-cleaner
Use profile-cleaner to reduce the size of browser profiles by organizing their sqlite databases using sqlite3's vacuum and reindex functions.

##Packages by Distro
* ![logo](http://www.monitorix.org/imgs/archlinux.png "arch logo")Arch via AUR Package: https://aur.archlinux.org/packages/profile-cleaner
* ![logo](http://chakra-linux.org/img/icon/chakra-kde_32.png "chakra logo")Chakra via CCR Package: http://chakra-linux.org/ccr/packages.php?ID=4501
* ![logo](http://freedos-32.sourceforge.net/lean/debian_logo.png "debian logo")Debian: See instruction below
* ![logo](http://sec-wall.gefira.pl/media/gfx/logo-fedora.png "fedora logo")Fedora: http://repo-ck.com/bench.htm#Fedora_RPMs
* ![logo](http://www.haskell.org/platform/icons/mint.png "mint logo")Mint: See instruction below
* ![logo](http://www.monitorix.org/imgs/ubuntu.png "ubuntu logo")Ubuntu: See instructions below
* ![logo](http://s23.postimg.org/5pabe2o5z/void_logo_transparent.png "void logo")Void: in the Void [repos](https://github.com/xtraeme/xbps-packages/tree/master/srcpkgs/profile-cleaner).
* ![logo](http://i.imgur.com/ooVjgFG.png "gentoo logo")Gentoo: See instructions below


###Debian Users
To add the PPA (personal package archive) to your Debian (tested on squeeze) system, and to install psd, do the following as the root user:

    echo "deb http://ppa.launchpad.net/graysky/utils/ubuntu quantal main" > /etc/apt/sources.list.d/graysky.list
    echo "deb-src http://ppa.launchpad.net/graysky/utils/ubuntu quantal main" >> /etc/apt/sources.list.d/graysky.list
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys FF7F9516
    apt-get update
    apt-get install profile-cleaner

###Mint Users
To add the PPA (personal package archive) to your Mint system (tested on 14.1), and to install psd:

    sudo add-apt-repository ppa:graysky/utils
    sudo apt-get update
    sudo apt-get install profile-sync-daemon

###Ubuntu Users
To add the PPA (personal package archive) to your Ubuntu (packages available for Lucid and newer) system, and to install psd:

    sudo add-apt-repository ppa:graysky/utils
    sudo apt-get update
    sudo apt-get install profile-cleaner

##Gentoo Users
To add the overlay to your Gentoo system:

    layman -a laurentb
    emerge profile-cleaner

###Other Distros
If you are interested in packaging psd for your favorite distro, please contact me.

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
