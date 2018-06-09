## Installing Lode Runner Mad Monks Revenge on Ubuntu

This set of instructions has been tested on Ubuntu 17.10. Contact timsims1717 (at) gmail (dot) com if you have problems or successfully install Lode Runner on a different distro.

install wine

`sudo apt install wine64`
`sudo dpkg --add-architecture i386`
`wine --version` to ensure the install was successful

wine is set to emulate 64 bit operating systems. We need 32 bits for Lode Runner

`env WINEARCH=win32 WINEPREFIX=$HOME/.wine32 winecfg`

this opens winecfg, but it also creates a .wine32 folder where your 32 bit programs will live

install Lode Runner MMR using the custom installer

`env WINEARCH=win32 WINEPREFIX=$HOME/.wine32 wine path/to/LodeRunner_MMR-signed.exe`

load up winecfg again

`env WINEARCH=win32 WINEPREFIX=$HOME/.wine32 winecfg`

* click Add Application
* navigate to the installed Lode Runner (should be $HOME/.wine32/drive_c/SIERRA/LODERUNN/LODERUNN.exe)
* make sure LODERUNN.exe is highlighted
* change the Windows Version to Windows 95
* click Apply
* select the Graphics tab
* check "Emulate a virtual desktop"
* click Apply

to run Lode Runner, use the following command.

`env WINEARCH=win32 WINEPREFIX=$HOME/.wine32 wine .wine32/drive_c/SIERRA/LODERUNN/LODERUNN.EXE`

if you want a shortcut to run it, add this line to $HOME/.bashrc:

`alias lrmmr="env WINEARCH=win32 WINEPREFIX=$HOME/.wine32 wine .wine32/drive_c/SIERRA/LODERUNN/LODERUNN.EXE"`

then run

`source $HOME/.bashrc`

you should now be able to run lode runner from the terminal by typing `lrmmr`