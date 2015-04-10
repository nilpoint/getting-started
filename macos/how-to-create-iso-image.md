1. Download the OS X bundle file, fox example, Install OS X Yosemite.app.
2. Right click the app bundle file, select 'Show Package Contents' , you can find the InstallESD.dmg file in the Contents/SharedSupport/ folder.
3. Open a terminal window, run the command as following,
$ hdiutil convert your/file/path/InstallESD.dmg -format UDTO -o your/file/path/Yosemite.iso
