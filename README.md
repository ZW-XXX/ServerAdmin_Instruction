# ServerAdmin_Instruction


1. Add new users by:
` sudo useradd -r -m -s /bin/bash {$usr_name$} `
Marks: (1) In the Ubuntu 18.04 system, it will not automatically prompt to set a password when adding a user. Therefore, you need to do it manually as:
` sudo passwd {$usr_name$} `
Some useful commends:
(2) #Args:
-r：Add a new account
-m：Automatically create user login directory
-s：Specify the shell used by the user after logging in
Once the users have been added, You can see that the user directory was successfully created by ` ls /home/ `

2. Create the data folder in for new users by:
` sudo mkdir /{$data_disk_path$}/{$usr_data_path$}`
Change the owner and group of the current file or directory into personality:
` sudo chown -r {$usr_name$} /{$data_disk_path$}/{$usr_data_path$}`
After specifying in this way, the authority of the file directory is on Tom, who can add, delete, modify and query it arbitrarily, and no one else, except the administrator, can access it.

