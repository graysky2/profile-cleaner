Use profile-cleaner to reduce the size of browser profiles by organizing their sqlite databases using sqlite3's vacuum and reindex functions.

Packaged for Arch Linux in the AUR: https://aur.archlinux.org/packages/profile-cleaner

Sample output and results using an "uncleaned" firefox profile:

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
