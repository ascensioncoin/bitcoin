
Debian
====================
This directory contains files used to package ascensiond/ascension-qt
for Debian-based Linux systems. If you compile ascensiond/ascension-qt yourself, there are some useful files here.

## ascension: URI support ##


ascension-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install ascension-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your ascension-qt binary to `/usr/bin`
and the `../../share/pixmaps/ascension128.png` to `/usr/share/pixmaps`

ascension-qt.protocol (KDE)

