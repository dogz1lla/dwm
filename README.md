# Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

```
make clean install
```


# Running dwm
Add the following line to your .xinitrc to start dwm using startx:

```
exec dwm
```

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

```
DISPLAY=foo.bar:1 exec dwm
```

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

```
    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm
```

# Patches
- systemcmd
- xresources
- vanitygaps
- ~~alpha~~ (NOTE: not using in the re-apply of patches)
- status2d

# Notes on patches
- use `git apply --reject --whitespace=fix your_patch.diff` to apply patches with git;
- vanitygaps is able to work with more than the set of the default layouts; so TODO is to patch `config.def.h` accordingly if new layouts are added;
- alpha requires composit window manager to work (eg picom); on VM it makes everything sluggish, should try enabling it on an actual machine;
