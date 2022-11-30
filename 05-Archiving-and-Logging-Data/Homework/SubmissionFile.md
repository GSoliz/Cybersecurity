## Week 5 Homework Submission File: Archiving and Logging Data

Please edit this file by adding the solution commands on the line below the prompt.

Save and submit the completed file for your homework submission.

---

### Step 1: Create, Extract, Compress, and Manage tar Backup Archives

1. Command to **extract** the `TarDocs.tar` archive to the current directory:

    `tar -xvf TarDocs.tar`

2. Command to **create** the `Javaless_Doc.tar` archive from the `TarDocs/` directory, while excluding the `TarDocs/Documents/Java` directory:

     `sudo tar -cvf Javaless_Docs.tar --exclude-tag=Java ~/Projects/TarDocs`

3. Command to ensure `Java/` is not in the new `Javaless_Docs.tar` archive:

    `tar -tf Javaless_Docs.tar | grep -rw Java *`

#### Critical Analysis Question

- Why wouldn't you use the options `-x` and `-c` at the same time with `tar`?

--- I would not use the command -c (create) and -x (extract) because you can not create an archive and extract the tar files from that archive at the same time.

### Step 2: Create, Manage, and Automate Cron Jobs

1. Cron job for backing up the `/var/log/auth.log` file:

    `6 * * 3 tar -czf /auth_backup.tgz /var/log/auth.log`

### Step 3: Write Basic Bash Scripts

1. Brace expansion command to create the four subdirectories:

    `sudo mkdir -p ~/backups/{freemem, diskuse, openlist, freedisk}`

2. Paste your `system.sh` script edits below:

    ```
    #!/bin/bash
    
    # Print free memory and save it to ~/backups/freemem/free_mem.txt
    free -h > ~/backups/freemem/free_mem.txt
    
    # Print disk usage and saves it to ~/backups/diskuse/disk_use.txt
    du -h >> ~/backups/diskuse/disk_usage.txt
    
    # lists all open files and saves it to~/backups/openlist/open_list.txt
    lsof > ~/backups/openlist/open_list.txt
    
    # Print file system disk space and saves it to~/backups/freedisk/free_disk.txt
    df -h >> ~/backups/freedisk/free_disk.txt
    ```

3. Command to make the `system.sh` script executable:

    `chmod +x system.sh`

**Optional**
- Commands to test the script and confirm its execution:

    ```
     Sudo ./system.sh
     sudo cat ~/backups/freedisk/free_disk.txt
     sudo cat ~/backups/freemem/free_mem.txt
     sudo cat ~/backups/diskuse/disk_usage.txt
     sudo cat ~/backups/openlist/open_list.txt
    ```

### Step 4. Manage Log File Sizes
 
1. Run `sudo nano /etc/logrotate.conf` to edit the `logrotate` configuration file. 

    Configure a log rotation scheme that backs up authentication messages to the `/var/log/auth.log`.

    - Add your config file edits below:

    ```
        /var/log/auth.log {
  	    
            Rotate 7
  	        weekly
  	        notifempty
  	        delaycompress
  	        missingok
 	        endscript
        }

    ```
---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
