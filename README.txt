# UnixCommands

Find all Java versions installed on Mac:
cd /usr/libexec
./java_home -V

Kill a process: KILL LIVY: ps -ef | grep livy
                kill -9 <id here>

Cat <filename> -> displays content of the file in command prompt itself 
More <filename> --> use spacebar to move to next page, b for back page, q to quit

Symlink:
Unlink a symlink: unlink <symlink name eg: latest>
Create a symbolic link: ln -s <full path to point to: /opt/tusker/livy/livy-0.7.0-1> <symlink name: latest>

SCP:
scp -r ./com ksharma@sl73tskrapd078.visa.com:/root/tusker-tests/ Or
scp ksharma@s173caehenc601.visa.com/export/home/ksharma/get_cluster_config_working.sh .

Access and Permissions:
ls-al
(file/directory) (rwe)-(rwe)-(rwe)
                  user  grp  other

chmod-R 755 <file or folder name use -R with folder only>
chmod u=rwx,g-rwx,o=rwx <filename>
chmod a+rwe <filename>
chmod u+r,u+w,u+e,g+r,g-w,g-e,o-r <filename> 
chmod g+rwx <filename> (adds write access to the group)
chmod u+w <filename> (adds write access to the user)
chmod a+w <filename> (adds write access to all: user, group and others)
chmod a-w <filename> (removes write access from all: user, group and others)

Change Owner:
chown -R : <grpname> <filePath or directory path> (changed the group to specified group for this file/dir)
chown root:hadoop /opt/tusker/livy/livy-0.7.0-1 
chown -c <new user name> <filename>

Create a new user:
Useradd -m <username> ---> we also need to set password for this user using: passwd <username>

Create a new Group: 
groupadd <new groupname>

Add a user into a group:
usermod -a -G <groupname> <username>. (Adds user into the group) 
(or Useradd-G <grpname> <ustname>)

Change group:
chgrp -v <groupname to be assigned> <filename>
Or
chgrp -R <groupname to be assigned> <foldername>

Setfacl -m g:<grpname>:rwx -

History (shows our commands list used. Then just use ! Followed by number)

mkdir <name>
mv <name1> <name2> 
cp <name1> <name2> -->files copy command
cp -R <foldername1> <foldername2> --> copy folder
rm <filename>
rm -Rf <folderName>

Find . -name file01 -print (finds a file01 inside current location) or Find . -name "file" -print 
Find . -type d -print (finds all directories inside current location) or Find . -type f -print

ls-al <filename> | grep -i <keyword> | cut -c25- | sort -nr -k1. (sends ls result to grep and then gives lines with keyword in it ignorecase and then we cut the result from left by 25 chars and take till last and then sort the result by numeric in reverse order and by column 1)

Grep:
Grep <keyword> <filename> (returns all occurences of keyword from the file case sensitively) 
Grep -i <keyword> <filename> (returns all occurences of keyword from the file ignore case) 
Grep -i-v <keyword> <filename> (returns lines without keyword in them ignore case)

Uniq (Distinct or No Duplicates):
Uniq <filename> (prints only unique lines from file) 
Uniq -c <filename> (prints unique lines from file and also mark total count against each line to tell duplicacy count) 
Uniq -d <filename> (prints only duplicate lines from file just once each)

Find differences or Compare tool: Diff <file1> <file2>

Sdiff <file1> <file2>.> MUCH MORE USEFUL

Translate uppercase to lowercase:

Cat <file1> | tr A-Z a-z (translates the content of file from uppercase to lowercase)

Cat file1 | tr A-Z a:z> newFile.txt

Untar a tar.gz file using:  tar -xvf <filename>
