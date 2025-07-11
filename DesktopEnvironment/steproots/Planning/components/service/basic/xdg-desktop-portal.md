# xdg-desktop-portal

## Interfaces

See https://flatpak.github.io/xdg-desktop-portal/docs/impl-dbus-interfaces.html and https://wiki.archlinux.org/title/XDG_Desktop_Portal.

* Access - xdg-desktop-portal-gtk
* Account - xdg-desktop-portal-gtk
* App chooser - xdg-desktop-portal-gtk
* Background - TODO
* Clipboard - TODO
* Dynamic launcher - xdg-desktop-portal-gtk
* Email - xdg-desktop-portal-gtk
* File chooser - xdg-desktop-portal-gtk
* Global shortcuts - TODO
* Inhibit - xdg-desktop-portal-gtk (?)
  * xdg-desktop-portal-gtk seems to use org.gnome.ScreenSaver
* Input capture - TODO
* Lockdown - UNMARKED
* Notification - xdg-desktop-portal-gtk
* Print - xdg-desktop-portal-gtk
* Remote desktop - TODO
* Screen cast - xdg-desktop-portal-wlr
* Screenshot - xdg-desktop-portal-wlr
* Secret
  * Can use gnome-keyring or kwallet
* Settings - xdg-desktop-portal-wlr, xdg-desktop-portal-gtk
* Wallpaper - TODO

In total, we need xdg-desktop-portal-gtk, xdg-desktop-portal-wlr, gnome-keyring or kwallet, and custom implementations of our own.
