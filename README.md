ubuntu tip
==========

### Change all associations from gedit to another application ###
```
sudo sed -i 's/gedit.desktop/sublime-text-3.desktop/g' /usr/share/applications/defaults.list
```

### Remove Wine's Notepad from “Open With” options ###
```
sudo sed -i 's/wine-extension-txt.desktop/sublime-text-3.desktop/g' ~/.local/share/applications/mimeinfo.cache
```

### Screen brightness
```
dbus-send --session --print-reply --dest="org.gnome.SettingsDaemon" /org/gnome/SettingsDaemon/Power org.gnome.SettingsDaemon.Power.Screen.SetPercentage uint32:**50**
```

### fix for network manager and suspend
```
vi /etc/default/acpi-support
STOP_SERVICES="networking"
```
### disable notebook keyboard
1.
```
lucas@lucas-ThinkPad:~$ xinput
⎡ Virtual core pointer                    	id=2	[master pointer  (3)]
⎜   ↳ Virtual core XTEST pointer              	id=4	[slave  pointer  (2)]
⎜   ↳ USB OPTICAL MOUSE                       	id=10	[slave  pointer  (2)]
⎜   ↳ TPPS/2 IBM TrackPoint                   	id=15	[slave  pointer  (2)]
⎜   ↳ SynPS/2 Synaptics TouchPad              	id=13	[slave  pointer  (2)]
⎣ Virtual core keyboard                   	id=3	[master keyboard (2)]
    ↳ Virtual core XTEST keyboard             	id=5	[slave  keyboard (3)]
    ↳ Power Button                            	id=6	[slave  keyboard (3)]
    ↳ Video Bus                               	id=7	[slave  keyboard (3)]
    ↳ Video Bus                               	id=8	[slave  keyboard (3)]
    ↳ Power Button                            	id=9	[slave  keyboard (3)]
    ↳ Integrated Camera                       	id=11	[slave  keyboard (3)]
    ↳ AT Translated Set 2 keyboard            	id=12	[slave  keyboard (3)]
    ↳ ThinkPad Extra Buttons                  	id=14	[slave  keyboard (3)]
```
2.
```
xinput float [AT Translated Set 2 keyboard id]
```
