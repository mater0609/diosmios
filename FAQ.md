#Mashup of frequently asked questions



![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# I just get a black screen (no DIOS MIOS splash screen) #
Chances are high that your USB2IDE device isn't supported.
  * Assure that your HDD is formatted with FAT32, no other FS is supported.
  * Only cluster sizes 32KB or less are supported.
  * Only 2TB drives or less are supported.
  * The FAT32 partition MUST be the first primaly partition on the HDD, otherwise it will not work.
  * If all the above are ok try another USB2IDE device or wait for an update.

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# I just get a black screen AFTER the DIOS MIOS splash screen #
Before anything check the [game issues](https://code.google.com/p/diosmios/wiki/GameIssues) wiki page.
> If your game isn't listed you should try the following:
  * Verify that your dump is ok, just google for the md5 hash.
  * Try to install the game with DiscEX (without -c)
  * Assure that the game isn't just waiting for the debugger
  * Try to use a game version that matches your region
  * Verify your loader settings and turn off things like NMM/Force-Prog, NMM/Force-Prog can cause black screens

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# It takes long for the DIOS MIOS splash screen to show up #
DIOS MIOS looks for an USB device on port 0 first and has code in place which waits for a device to become ready, only after (10seconds) it tries port 1.
  * Simply connect your device to port 0 instead.

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# I get a green screen after the DIOS MIOS splash screen #
This usually can have three reasons:
  * You have the debugger with waiting enabled
  * The game just crashed (should get a crash dump via USBGecko if `__`fwrite patch was applied)
  * The game tried to switch from one video mode to another, usually happens when loading USA games on EUR systems or vice versa.

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# I get "Fatal error app\_main:dst not in MEM1!" #
GCLoader got incorrect data when reading from the ISO
  * Verify that your HDD is using 32KB cluster size or less, this error can happen with 64KB cluster size.
  * Verify that your dump is ok, just google for the md5 hash.
  * Try to install the game again (delete the old folder before)

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# I get "Fatal error apploader size is zero!" #
This means DM was unable to mount the selected ISO for whatever reason.
  * Verify that your dump is ok, just google for the md5 hash.
  * Try to install the game again (delete the old folder before)
  * Your loader is using an incorrect config version
  * You installed DIOS MIOS and are trying to load a game from SD card
  * You installed DIOS MIOS Lite and are trying to load a game from an USB device

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# I get "Fatal error entrypoint is not within MEM1!" #
This means the apploader could not load the main.dol
  * Verify that your dump is ok, just google for the md5 hash.
  * If you used GCReEX or DiscEX -c try DiscEX without -c to install the game as some games might break if you modify them
  * Try to install the game again (delete the old folder before)


![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# My system shuts down when using NMM while loading/saving #
  * In short NMM isn't supported for that game.
  * This means a fatal error occurred in the NMM code and it could no longer assure stable program execution.

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# NoDisc patch doesn't work #
  * It seems many loaders havn't caught up yet since NoDisc is no longer controlled via the config but instead just but either having a disc in the drive or not.

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# Will NTFS ever be supported? #
  * No, it would also take way more space than there is available. Just so you know libNTFS for Wii/GC is about 500KB, total memory DM can use is 96KB and almost everything is already used up.

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# Will the Wiimote/Classic Controller ever be supported? #
  * No, this would require a complete SDIO/BlueTooth/Wiimote lib, which would also take up way more space than available. (BT+Wiimote lib in libOGC are ~600KB).

![http://det1re.de/a/sneek/sneek_div.png](http://det1re.de/a/sneek/sneek_div.png)
# Will WBFS ever be supported? #
HAHA nice joke.