# How To setup/create a triple-boot with MacOS Boot Manager Icons on a  2019 MBP

## *Difficulty Level: Medium-Hard*

### ==Needed== *to complete*

- 2019 MBP
- Windows 10 Setup ISO
- Rufus for Windows
- Windows 11 Setup ISO
- EndeavourOS-Mercury-T2 (Linux) ISO
- Custom MacOS Boot Manager Icon(s) Per OS

## Level 1 Setup

1. Must have MacOS installed to start
     Reboot into "Recovery Mode" (hold Apple (Cmd)+R)
   - Under "Utility" menu
   - Open "Terminal"
   - Type `csrutil disable`
2. Use Bootcamp via MacOS to install Windows 10
3. Set Windows partion size according which OS gets the most traffic (There are going to be 3) **Once Finished**
4. Finish Windows 10 setup by installing Windows Bootcamp Drivers
5. Install Rufus for Windows -- Make Bootable Windows 11 USB (using ISO)
6. Upgrade Windows 10 > Windows 11 from Windows 10 with Rufus Windows 11 USB (This will allow install on **"Non-Compliant"** PC)

## Level 2 setup

1. Install Bluetooth
```
sudo pacman -S bluez bluez-utils
```
2. Start Bluetooth
- `sudo systemctl start bluetooth`
3. Enable Bluetooth on Boot
- `sudo systemctl enable bluetooth`
4. Install Bluetooth GUI
- `sudo pacman -S blueman`
- --OR
- `sudo pacman -S blueberry`
5. Troubleshooting (if FAIL)
```
sudo bluetoothctl
power on
agent on
default-agent
scan on
pair <MAC Address>
trust <MAC Address>
connect <MAC Address> 
```

## MacOS

1. Using Disk Utility -- Create 3 New Partitions (4 if a standalone data disk desired) each will be reformatted during EndeavourOS Installation
1. 500MB?? MSDOS FAT16 -- Format
2. 16GB APFS -- whereas 16GB = MBP RAM
3. 200GB APFS -- whereas 200GB = MBP Available disk space
