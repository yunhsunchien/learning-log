
Week 01 · Day 1 — Linux file system & permissions
Date: 2026-11-16 · Environment: Killercoda (Ubuntu 24.04)

1. Directory structure
Path	What's inside
/home/<user>, /root	User home folders
/etc	Config files (e.g. /etc/hosts, /etc/os-release)
/var/log	Logs
/usr/bin	Programs
/tmp	Temp files
2. Commands I used
pwd                      # where am I
ls -la                   # list all files with details
cd ~ / cd .. / cd /etc   # move around
cat /etc/os-release      # read a file
mkdir -p lab/day1        # create nested folders
touch notes.txt          # create empty file
echo "hello" > a.txt     # overwrite
echo "hello" >> a.txt    # append
cp / mv / rm             # copy / move-rename / delete (no recycle bin!)
chmod 755 hi.sh          # change permissions
3. Permissions
-rw-r--r-- = type + owner(u) + group(g) + others(o)

1st char: - file, d directory
Each group of 3 = r w x; a - means that permission is OFF
r = 4, w = 2, x = 1 → add up per group
Number	Letters	Use
755	rwxr-xr-x	scripts, directories
644	rw-r--r--	normal files
600 / 400	rw------- / r--------	SSH private keys
777	rwxrwxrwx	never on servers
4. Mistakes I made (and fixed)
cat /etc → "Is a directory". cat reads files; use ls for folders.
> hi.sh on its own line creates an EMPTY file. The redirect must be on the same line: echo 'echo "my first script"' > hi.sh
Missing spaces: echo"hi" becomes one unknown command. Spaces separate command and arguments.
Started in /, so lab/ was created at /lab. Check pwd first.
5. Quiz (4/5) and corrections
chmod 640 → group gets 4 = r-- → can read, cannot write. (I first wrote -w-; that would be 2.)
chmod 400 key.pem 
drwxr-x--- = directory, 750 ✅
> overwrites, >> appends ✅
Corrected English:
We should not set a website folder to 777, because every user, including attackers, could modify the files or upload malicious scripts.

Next
Day 2: grep, pipes |, vim

