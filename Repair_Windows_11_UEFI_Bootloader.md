# Windows 11 on GPT hdd, boot mode: UEFI

Problem: Failed to boot due to EFI broken

# Solution: Use Diskpart to Fix UEFI Boot Error in Windows 11

Requirement: USB contains windows 11 (Installation Media).

Steps:

Insert the Media (DVD or USB) in your personal computer and restart.

Boot from the media.

Select Repair Your Computer.

Select Troubleshoot.

Select Advanced Options.

Choose Command Prompt from the menu:

Type and run the command:

    diskpart
    
Type and run the command:

  list disk

Press enter

(Verify correct disk on which Windows 11 is installed)

Type and run the command:

    select disk <number of volume>

(make sure to select correct number, for example: 0)

Type and run the command:

    list vol

Verify that the EFI partition (EPS - EFI System Partition) is using the FAT32 file system. Assign a drive letter to it that is not already in use: example z:

    select vol <number of volume>
    
(e.g.: select vol 2)
    
Type and run the command:

    assign letter=z
        
Wait for the confirmation message from the diskpart utility to appear:

    DiskPart successfully assigned the drive letter or mount point.

Then type:

    exit

Press Enter

Then type:

    cd /d z:\EFI\Microsoft\Boot

(Make sure to replace z: with the letter you’ve assigned earlier)

Press Enter

Then type:

    bootrec /fixboot

Press Enter

Then type:

    ren BCD BCD.Backup

This will create a backup of your current BCD file.

Press Enter

Then type:

    bcdboot c:\Windows /l en-us /s z: /f ALL

(Make sure to replace z: with the letter you’ve assigned earlier)

Press Enter

Remove the install media from the disc tray or USB port

Type:

    exit

Press Enter

Restart the computer

(Note: maybe reboot the first time didnot success, but the second does. Also, make sure to boot on UEFI mode and choose correct disk/partition)


