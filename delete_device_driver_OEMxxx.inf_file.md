 Script to find and delete device driver OEMxxx.inf file

I need some guidance on how I might programmatically automate these steps below, with powershell or whatever:

    Open Device Manager

    Find either the ELAN or Synaptics SMBus Driver.

    Right click the SMBus Device and Select Properties.

    Select the Details tab.

    Scroll down in the Property field, to find INF name.

    Make note of the oemXXX.inf file name.
    📷

    If a non-Intel SMBus driver is present, run the following command via admin Command Prompt.

    Change to the \windows\system32\DriverStore\FileRepository.

    Type pnputil /delete-driver oemXXX.inf /uninstall /force
