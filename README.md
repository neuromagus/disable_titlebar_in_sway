# disable titlebar in sway

This patch for latest Sway (1.10) and old version (1.9) which adds the ```disable_titlebar``` option in the config file.

Instruction:
1. Download latest Sway-1.10 source tarball: https://github.com/swaywm/sway/archive/refs/tags/1.10.tar.gz
2. Download patch for latest Sway (1.10): [disable_titlebar_patch_sway1-10.tar.gz](https://github.com/neuromagus/disable_titlebar_in_sway/releases/download/v1.10/disable_titlebar_patch_sway1-10.tar.gz)
3. Extract Sway-1.10 tarball
4. Extract patch and move to sway-1.10 folder
5. Go to the sway-1.10 folder and apply the patch
6. Compile and install sway (if you want use old Sway version, you need add this command for use old Wlroots!
On Archlinux, for example, use this command:  
```export PKG_CONFIG_PATH='/usr/lib/wlroots0.17/pkgconfig``` before ```meson build/```):

```
tar xf sway-1.10.tar.gz
tar xf disable_titlebar_patch_sway1-10.tar.gz; mv disable_titlebar_sway1-10.patch sway-1.10/
cd sway-1.10/; patch -p1 < disable_titlebar_sway1-10.patch
meson build/
ninja -C build/
sudo ninja -C build/ install
```

7. Edit ```~/.config/sway/config``` file and add the option: ```disable_titlebar yes``` or read ```man 5 sway``` xD.  
For example, a piece of my ~/.config/sway/config:
```
workspace_layout tabbed
default_border none
default_floating_border none
disable_titlebar yes
```

Enjoy.


