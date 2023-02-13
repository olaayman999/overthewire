```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
username:password => _bandit13 : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw_
![image](https://user-images.githubusercontent.com/72671239/218564962-a5eb2ee4-87df-4917-9855-c5f2a0d9222a.png)

once connected, start inspecting
![image](https://user-images.githubusercontent.com/72671239/218581389-99dcada1-c61f-445c-a75b-232f6659f0a8.png)

```text
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14.
For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level.
Note: localhost is a hostname that refers to the machine you are working on
```
i tried connecting to the ssh via the default port (22) but it didn't work
![image](https://user-images.githubusercontent.com/72671239/218581727-de0e2bc3-4bba-4c85-acfa-fa6ac12e374b.png)

so i tried the 2220 port and it worked
```bash
ssh -i sshkey.private bandit14@localhost -p 2220
```
![image](https://user-images.githubusercontent.com/72671239/218581983-275a49e6-eb2a-4c3f-80d3-3bd139f134c7.png)
![image](https://user-images.githubusercontent.com/72671239/218582031-381d9336-eccf-4341-8bce-a5f5a972997b.png)

_bandit13 => fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq_

notes:

[key-based SSH](https://github.com/olaayman999/overthewire/blob/main/bandit/notes/key-based_SSH.md)
