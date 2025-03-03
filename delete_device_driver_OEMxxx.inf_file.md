 Script to find and delete device driver OEMxxx.inf file

Find INF name.
Make note of the oemXXX.inf file name.
Run the following command via admin Command Prompt.


    Change dicectory to the \windows\system32\DriverStore\FileRepository (cd \windows\system32\DriverStore\FileRepository)

    Type 
    
    pnputil /delete-driver oemXXX.inf /uninstall /force
