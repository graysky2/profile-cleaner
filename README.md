# Profile-cleaner
Use profile-cleaner to reduce the size of browser profiles by organizing their sqlite databases using sqlite3's vacuum and reindex functions.

## Dependencies
* bc
* findutils
* sqlite
* parallel (new dependency)

## Links
AUR Link: https://aur.archlinux.org/packages/profile-cleaner

## Sample Output and Results Using an "Uncleaned" Firefox Profile:

	Size before: 154.17 Mbytes
	Size after:  99.11 Mbytes
	Recovered:   55.06 Mbytes

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

## Speed Comparison
28-Nov-2012		Profile-cleaner has been rewritten to use GNU Parallel for processing.

Here is a contrived example syncing 6 firefox profiles comparing the classical version of Profile-cleaner which used for loops to process profiles to the new version:

* There are a total of 312 M in the 6 "dirty" profiles.
* Test machine is an Intel 3770K @ 4.50 GHz.
* After cleaning there is a total of 213 M in the 6 "clean" profiles.

new 4.07s user 0.42s system 318% cpu 1.411 total

old 8.15s user 0.43s system 95% cpu 8.942 total

Your mileage may vary.
