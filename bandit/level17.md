create a file that contain the whole private key generated from bandit16, then change the permissions using chmod command

![image](https://user-images.githubusercontent.com/72671239/218629165-6655d54b-ec8f-4131-81d6-b31168cc6df7.png)

`chmod 400` sets the file permission of a file to `r--------`, which means that only the owner of the file has read permission, and all other users (including the group that the owner belongs to) have no permission to read, write, or execute the file.

In other words, `chmod 400` sets the file permission to read-only for the owner of the file, with no permission granted to any other user on the system. This permission is often used to protect sensitive files, such as private SSH keys or other configuration files that contain confidential information, from being accessed or modified by unauthorized users.

```bash
ssh -i private_bandit16.txt  bandit17@bandit.labs.overthewire.org -p 2220
```
use this command and no need to type any password like usual
![image](https://user-images.githubusercontent.com/72671239/218630403-1f68fcc1-344b-4bf9-82f6-6cb5f2f7e498.png)

i solved this challenge using 2 ways, one is by combining the password.new and password.old files into a new files in the /tmp/mynewdir/newfile.txt then finding unique lines and seeing which one is in the password.new

![image](https://user-images.githubusercontent.com/72671239/218631477-38638956-3e40-4df5-be82-7dc31d3ab3cb.png)

the other way using diff command 

diff stands for difference. This command is used to display the differences in the files by comparing the files line by line

![image](https://user-images.githubusercontent.com/72671239/218631753-4a118784-a3f2-460d-91fc-ac61b3c9bd0b.png)

_bandit17 => hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg_
