# disable titlebar in sway

this patch for Sway 1.9 which adds the 'disable_titlebar' option in the config file.

Instruction:
1. Download latest Sway-1.9 source tarball: https://github.com/swaywm/sway/archive/refs/tags/1.9.tar.gz
2. Download patch: [disable_titlebar_patch.tar.gz](https://github.com/neuromagus/disable_titlebar_in_sway/blob/main/disable_titlebar_patch.tar.gz)
3. Extract Sway-1.9 tarball
4. Extract patch and move to sway-1.9 folder
5. Go to the sway-1.9 folder and apply the patch
6. Compile and install sway
(now we have different versions of Wlroots.
On Archlinux, for example, use this command:  
```export PKG_CONFIG_PATH='/usr/lib/wlroots0.17/pkgconfig``` before ```meson build/```):

```
tar xf sway-1.9.tar.gz
tar xf disable_titlebar_patch.tar.gz; mv disable_titlebar.patch sway-1.9/
cd sway-1.9/; patch -p1 < disable_titlebar.patch
meson build/
ninja -C build/
sudo ninja -C build/ install
```


7. Edit ```~/.config/sway/config``` file and add the option: ```disable_titlebar yes``` or read ```man 5 sway``` xD.  
For example, a piece of my ~/.config/sway/config:
```
xwayland disable
workspace_layout tabbed
default_border none
default_floating_border none
disable_titlebar yes
```

Enjoy.

***
Thanks to y0nei for the feedback, I added a fix for drawing the top border.
***

