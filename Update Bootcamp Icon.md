# Update BootCamp Desktop Icon
>
> To update the internal Boot Camp desktop icon on macOS, you can follow these steps:

## Steps

- Ensure System Integrity Protection (SIP) is disabled by booting into Recovery Mode (hold Command + R during startup), opening Terminal, and running csrutil disable. 
- Copy the desired .icns file to /System/Volumes/Preboot/.VolumeIcon.icns for the macOS volume or /Volumes/EFI/.VolumeIcon.icns for the Windows EFI partition.
  For example:
   ```
   sudo cp /path/to/your/icon.icns /System/Volumes/Preboot/.VolumeIcon.icns
   ```
   **OR**
   ```
   sudo cp /path/to/your/icon.icns /Volumes/EFI/.VolumeIcon.icns
   ```
- **Re-enable SIP** by booting back into Recovery Mode and running csrutil enable in Terminal. 
- Reboot your Mac and check if the icon has been updated in the Startup Manager and on the desktop. 

## Be Aware...

- Note that Finder might overwrite custom icons, and some users have reported issues with certain macOS versions or hardware configurations. 
- If you are using an external drive, the process might be different, and the .VolumeIcon.icns file might disappear after a short time due to Finder's behavior. 

For macOS Mojave and earlier, you can also try changing the icon through the Get Info window, but this method may not work for all users or on all systems.

> Remember to ensure the .icns file is correctly formatted and placed in the appropriate directory to avoid issues.
