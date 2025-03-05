https://github.com/ramensoftware/windhawk/discussions/155#discussioncomment-8495683

Copy the following folders:

    %ProgramData%\Windhawk\Engine\Mods
    %ProgramData%\Windhawk\ModsSource

To make things easier, I:

    Created a folder called "Windhawk Backup"
    Copied the ModsSource folder to it
    Added a subfolder called Engine
    Copied the Mods folder to the Engine subfolder.

And, using REGEDIT, save the following key (I saved mine to my Windhawk Backup folder):

    HKEY_LOCAL_MACHINE\SOFTWARE\Windhawk

I did this when I was switching over to a new computer. Once I backed up the above from the old computer, I installed Windhawk on my new one, then:

    Copied the contents of my Windhawk Backup folder except the registry key to the Windhawk folder. When asked to replace something, clicked Replace or Okay.
    Double-clicked on the registry key to add it to the registry.

This successfully migrated all the mods and settings to my new computer.

**When using REGEDIT, be careful not to delete or modify anything. You only need to Save the key.
