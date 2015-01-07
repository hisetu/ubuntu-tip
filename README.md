ubuntu tip
==========

### Change all associations from gedit to another application ###
sudo sed -i 's/gedit.desktop/sublime-text-3.desktop/g' /usr/share/applications/defaults.list

### Remove Wine's Notepad from “Open With” options ###
sudo sed -i 's/wine-extension-txt.desktop/sublime-text-3.desktop/g' ~/.local/share/applications/mimeinfo.cache
