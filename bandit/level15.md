```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```
username:password => _bandit15 : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt_

![image](https://user-images.githubusercontent.com/72671239/218610339-bdded226-ffed-477a-891d-0b6c11a5d9ff.png)

once connected, start inspecting

the `nc` doesn't have commands for ssl, but `ncat` does

![image](https://user-images.githubusercontent.com/72671239/218611907-b2323e9b-6581-46ea-a6ce-229988ba8867.png)

connect to the ncat server and paste the current password

![image](https://user-images.githubusercontent.com/72671239/218613132-119d61f0-e29b-4d05-9441-6c1b5e0ff3bb.png)


_bandit15 => JQttfApK4SeyHwDlI9SXGR50qclOAil1_

notes: [ncat ssl](https://github.com/olaayman999/overthewire/blob/main/bandit/notes/ncat_SSL.md)
