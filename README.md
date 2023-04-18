# ServerAdmin_Instruction



1. Add new users by:  
``` sudo useradd -r -m -s /bin/bash {$usr_name$} ```
Some useful commends:  
(1) #Args:  
`-r`：add a new account  
`-m`：automatically create user login directory  
`-s`：specify the shell used by the user after logging in  
Once the users have been added, You can see that the user directory was successfully created by `ls /home/`  
(1) In the Ubuntu 18.04 system, it will not automatically prompt to set a password when adding a user. Therefore, you need to do it manually as:  
``` sudo passwd {$usr_name$} ```  
  
2. Create the data folder in for new users by:  
` sudo mkdir /{$data_disk_path$}/{$usr_data_path$}`  
Change the owner and group of the current file or directory into privacy:  
` sudo chown -r {$usr_name$} /{$data_disk_path$}/{$usr_data_path$}`  
After this specification, the authority of the file directory is on `{$usr_name$}`, who can add, delete, modify and access it arbitrarily, and anyone else, except the administrator, can only access it.  
  
3. Materials  
(1) Toolbox installation package  
Compared with other toolboxes, we would rather providing `Anaconda` installation packages than others. It is worth mentioning that `docker` is also supported and has installed on both server. However, docker often takes up more storage space when creating a single environment variable sample.  
I tend to update the Anaconda installation package in `/home/{$home_admin_path$}/Downloads/` every quarter, and copy a sample for each new user in their home directory `/home/{$home_usr_path$}/`.  
(2) README file  
I keep a brief README file for each new user available at `/home/{$data_admin_path$}/Downloads/README.txt`, and copy a sample for each new user in their home directory `/home/{$home_usr_path$}/`. Its content mainly includes:  
    * The configuration of the Server, including the number of GPUs, memory capacity, NVIDIA-Driver version, and CUDA version.  
    * User rule 1: Environment files can be placed in the home directory, while codes and databases should be placed in the data directory.  
    * User rule 2: The pytorch version needs to be higher than 1.7 and above. Please update the code to suit Pytorch Version 1.7.0 or above. (Admin Rule: As an Admin, please do not update the CUDA version easily.)  
    * User rule 3: Please be careful with every command type in because it can be a potential risk. Particularly, please use commend `rm` with caution.  
    * User rule 4: Debugging on the server is not allowed.  
    * User rule 5: For security, we do not allow our servers to connect to Internet.    
(3) Public Database  
Public databases are established to serve the research needs of most users in our group, including `imagenet`, `mscoco2017`, `mscoco2014`, most IQA databases and most DVC databases. 
