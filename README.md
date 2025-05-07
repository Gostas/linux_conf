# My Linux configuration files

## Useful notes about setting up the GUI

https://askubuntu.com/questions/66195/what-is-a-tty-and-how-do-i-access-a-tty/66198#66198
By default, Ubuntu has 7 tty's.

On Ubuntu 17.10 and newer: It's GUI login screen on 1, GUI desktop on 2 and command lines on 3-7.
Up until Ubuntu 17.10: 1-6 are command line only and 7 runs your X session (your normal desktop).
To access them, use this keyboard shortcut:

Ctrl + Alt + F3 (or F1 until 17.10).


Use loginctl to view gui sessions details and kill/terminate them

Empty journalctl logs:
journalctl --rotate --flush
journalctl --vacuum-time=1s
rm -rf /var/log

Many configuation options in /etc/, e.g. /etc/(gdm3 | lightdm | xdg)
More configs in /usr/share, e.g. /usr/share/wayland-sessions
User configs in ~/.config

https://forums.raspberrypi.com/viewtopic.php?t=294014
Autostart programs for RPi: /etc/xdg/autostart and ~/.config/autostart

https://wiki.archlinux.org/title/Plymouth
Wait for plymooth animation to complete: Create /etc/systemd/system/plymouth-wait-for-animation.service and enable this service

Install gdm3, libpam-gnome-keyring (fix not being able to login after logout)

LXSession setup: https://github.com/lxde/lxsession?tab=readme-ov-file
LXSession doesn't work with Waylanb

gnome-session only supports the gnome DE, pain to setup with sway

Only uwsm works https://github.com/Vladimir-csp/uwsm
