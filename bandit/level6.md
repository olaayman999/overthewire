```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```
username: password => _ bandit6 : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU_

![image](https://user-images.githubusercontent.com/72671239/218419737-529a9654-1cc0-49fc-89d2-e9294f6c776a.png)

once connected, start inspecting

```text
The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size
```

```bash
find / -type f -user bandit7 -group bandit6 -size 33c
```

![image](https://user-images.githubusercontent.com/72671239/218419487-a8ba24ed-af42-4165-b607-9573b937ef68.png)

remove the `permission denied ` clutter

You can hide errors from the terminal output by redirecting the standard error stream (stderr) to `/dev/null`. This can be done using the `2>` operator in the shell.

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2> /dev/null
```

![image](https://user-images.githubusercontent.com/72671239/218419249-4eb3b0b7-bbe5-4769-9eb9-ca861ae1512c.png)
_bandit6 => z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S_
