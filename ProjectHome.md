### **Features:** ###
  * Full speed loading from an USB device, or a SD card (DIOS MIOS Lite)
  * Loads 1:1 and compressed .ISO disc images
  * Loads games as extracted files (FST)
  * Loads retail discs
  * NMM (No More Memory) memory card emulation
  * Cheat code and WiiRd support
  * Changeable configuration of various settings
  * Reset/Power off via button combo (R + Z + Start) (R + Z + B + D-Pad Down)
  * Both internal NAND and SNEEK/UNEEK DI support
  * Advanced video mode patching and force 16:9 widescreen
  * In-game screen snapshots (R+Z on controller 4)
  * Automatic .ISO switching for multi disc titles

### **What DIOS MIOS doesn't do yet:** ###
  * Allow use of the Nintendo GameCube Microphone
  * Play backups from writable DVD media
  * Play audio via disc audio streaming

### **[Official DIOS MIOS (Lite) Compatibility List](http://crediar.no-ip.com/gc/)** ###
We are still looking for competent contributors  (JPN and 480p results especially)
Please come to #DM on EFnet if you want to help!

Before you use this software, make sure that your Wii has GameCube support. Wiis sold after late 2011 lack the GameCube controller and memory card ports, and can make no use of DIOS MIOS.

**DIOS MIOS (DM)** Format your USB devices 1st primary partition to FAT32 with 32KB cluster size or less. DM is looking on USB port 0 first, so if it takes a long time for the splash screen to appear, connect your device to the other port. If no splash screen appears at all, your HDD (usually the USB controller device is at fault not the HDD itself) is probably not supported. Slow HDDs seem to prove problematic for the faster extracted file (FST) format, so try .ISO first.

**DIOS MIOS Lite (DML)** Format your SD card to FAT/FAT32 with 64KB cluster size or less.

You can only either have DM, or DML installed to the internal NAND FS at once; not both. You can however use the latest revision of [SNEEK DI](http://code.google.com/p/sneek/) to browse titles stored on both USB and SD, and launch either DM or DML automatically.

The folders that DiscEX, GCReEx, and DMToolbox output are to be copied into a folder titled 'games' in the root of the USB or SD respectively. It's also very important to make sure your preferred backup loading software is up to date, and properly configured for use with the latest DM(L) release. If you need to use an accessory in slot B, enable 'Cheats' in your loader otherwise DM is patching fwrite where it's expecting a USB Gecko in that slot.

#DM and #SNEEK on EFNet

Still under heavy development and ongoing progress.

**Code revisions are no longer treated as the version!**
## **Change log:** ##
**2.11**
(2014-07-02)
  * Added the FatFS link map feature which should greatly decrease load times

**2.10**
(2013-05-24)
  * Fixed a bug in the pattern detection code (DVDLowReadDiskID)

**2.9**
(2013-04-05)
  * Changed patch code to prevent false hits (DVDLowReadDiskID)
  * Added C\_MTXLightPerspective patching (Fixes heat effects when using wide screen hack in Zelda:WW)

**2.8**
(2013-02-24)
  * Fixed a bug in GCLoader that broke the progressive patch
  * Moved progressive patch back 16 bytes, this fixes PADHOOK and progressive patching not working at the same time

**2.7**
(2013-02-20)
  * Fixed a bug that caused a black screen when using PADHook and Progressive mode patching at the same time

**2.6**
(2012-12-01)
  * Reduced HDD read time out to 25 seconds
  * Added two disc supports (Extracted format is unsupported)

**2.5**
(2012-11-09)
  * Fixed a bug in DM that could cause a fatal read error when using devices with under 8GB size
  * Added a PADHOOK pattern for Batman:Vengeance
  * Added a screenshot feature
> This feature can be enabled/disabled via the DM(L) config
> Press R+Z on the fourth controller to take a screenshot any time!
> Screenshots will be saved to /screenshots/ in the YPbPr format. Use the included YCbYCr2BMP to convert them

**2.4**
(2012-10-21)
  * Fixed NMM for Mario Kart Double Dash. Saving ghost data works now as well
  * Fixed a bug that would sometimes break cheating/debugging unless both were enabled
  * Moved the VIConfigure patch to the ARM side which should fix a number of broken titles
  * Changed the HDD time out to read a random sector
  * Optimised the EHCI reset code
  * Optimised the CARD code

**2.3**
(2012-09-24)
  * Fixed creating NMM save file folders in FST mode
  * Fixed CardFindEntryByName which incorrectly compared file names
  * Added a hack for Phantasy Star Online 1&2 version 1.0
  * GCLoader improvements that include warning the user if an incorrect CONFIG\_VERSION is used
  * Hardcoded the only worthy DVDGetDriveStatus patching, so once again the NODISC cfg doesn't do anything

**2.2**
(2012-07-20)
  * Added a new DVDLowRead pattern (fixes Luigi's Mansion USA and maybe other games)
  * Made the DVDGetDriveStatus patch optional via a config (DML\_CFG\_NODISC) since it broke some games  (fixes Prince of Persia:Sands of Time, Goblin Commander, King Kong, ...)

(2012-07-18)
  * Added code to prevent drives going into sleep mode
  * Fixed a bug which ignored the DML\_CFG\_PADHOOK setting and always patched PADHOOK (fixes PSO1&2)

**2.1**
(2012-07-17)
  * Config is now at version 2! Loaders will require an update
  * Improved patch code and made it more versatile
  * Improved .elf patching code (fixes Nightfire)
  * Improved No Disc patching
  * Added a hack for PSO I&II EUR/USA
  * Added the wide screen hack by Extrems
  * The NODISC config setting has been removed since it hasn't been used in 1.0+
  * Removed USBGecko debug output

**2.0 'BETA'**
(2012-07-08):
  * Fixed a bug which broke retail disc loading
  * Fixed a bug which ignored if DML\_CFG\_PADHOOK was set or not (always patched PADHOOK in)

(2012-06-30):
  * Fixed a bug which copied BI2 to the wrong address (fixes Pikmin)

(2012-06-29):
  * Fixed the Muppet error
  * Fixed some video stuff in GCLoader

(2012-06-28):
  * Added a new method of video mode forcing
  * PADHook patch is now working for retail discs again
  * Removed video mode force code from GCLoader
  * Removed VIConfigure sane mode switch patch

(2012-06-24):
  * Added EHCI retry code, which should fix a few more USB devices that weren't working before.
  * Fixed a DSI crash when using the progressive mode.
  * Fixed prog mode patch
  * Fixed a bug which prevented the SRAM settings to be flushed
  * Added a patch which fixes a green screen in certain cases

(2012-06-23):
  * Improved the USB/EHCI code, it now retries if an USB device fails to initialize.
  * Fixed some memory leaks