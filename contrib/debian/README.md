
Debian
====================
This directory contains files used to package baasd/baas-qt
for Debian-based Linux systems. If you compile baasd/baas-qt yourself, there are some useful files here.

## baas: URI support ##


baas-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install baas-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your baasqt binary to `/usr/bin`
and the `../../share/pixmaps/baas128.png` to `/usr/share/pixmaps`

baas-qt.protocol (KDE)

