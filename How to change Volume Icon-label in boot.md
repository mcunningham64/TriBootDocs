# How to change Volume Icon-label in boot
[How to change boot manager icons and labels](https://apple.stackexchange.com/questions/410374/how-do-i-change-the-icons-and-labels-in-the-macos-boot-manager)

## Rename “EFI Boot” in Startup Manager:
*Open up a Terminal and use the following commands:*
`diskutil list` - use this to find the Windows EFI partition
`sudo diskutil mount disk0s1` - whereas "disk0s1" is your EFI partition
`sudo bless --folder /Volumes/EFI/EFI/Boot --label Windows` - whereas **"Windows"** is your label of choice

## Rename “Macintosh HD” in Startup Manager
*Similar to above, but:*
`sudo bless --folder /System/Volumes/Data --label MacOS` - whereas **"MacOS"** is your label of choice

### Missing/Wrong Boot Manager Icon
*Reboot in recovery mode (command+R at boot) and use a terminal to run*
`csrutil disable`
-- which **disables SIP protection**
#### For Mac side:
`sudo cp /System/Library/Extensions/IOStorageFamily.kext/Contents/Resources/Internal.icns /System/Volumes/Preboot/.VolumeIcon.icns`

This will change the Mac/Macintosh HD boot icon to the default internal drive icon, but you can just copy whatever .icns file you wish to that location. See other posts for info on making your own .icns files.

#### For Windows side:
`sudo diskutil mount disk0s1` - Whereas disk01 is the name of your Windows EFI partition from above
`sudo cp /System/Library/Extensions/IOStorageFamily.kext/Contents/Resources/Internal.icns /Volumes/EFI/.VolumeIcon.icns`

*Don't forget to **enable SIP protection** again, if you wish, by booting back into recovery mode and using:*
`csrutil enable`