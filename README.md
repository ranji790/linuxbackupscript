Backup Script

This Bash script automates backing up files from a target directory to a destination directory. It only includes files modified in the last 24 hours and compresses them into a timestamped .tar.gz archive.

---

## Features

- Validates command-line arguments and directory paths.
- Detects files updated in the last 24 hours.
- Creates a compressed archive (.tar.gz) of updated files.
- Moves the backup archive to a specified destination directory.
- Can be scheduled with cron for automated backups.

---

## Usage


./backup.sh <target_directory> <destination_directory>

Example:

./backup.sh /home/user/important-documents /home/user/backups

<target_directory> – Directory to backup.

<destination_directory> – Directory where the backup archive will be saved.



---

How it works

1. Checks if exactly two arguments are provided.


2. Validates that the provided directories exist.


3. Sets variables for current timestamp, backup filename, and absolute paths.


4. Finds files modified in the last 24 hours.


5. Adds those files to an array.


6. Compresses the files into a .tar.gz archive.


7. Moves the archive to the destination directory.




---

Cron Setup (Optional)

You can schedule this script to run automatically using cron. Example to run every 24 hours:

crontab -e

Add the following line:

0 0 * * * /usr/local/bin/backup.sh /home/user/important-documents /home/user/backups

Start the cron service if it is not running:

sudo service cron start


---

Requirements

Linux or Unix-like system

Bash shell

tar command



---

License

This project is free to use and modify.
