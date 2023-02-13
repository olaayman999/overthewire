```bash 
ssh bandit5@bandit.labs.overthewire.org -p 2220
```
username:password => _bandit5 : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR_

![image](https://user-images.githubusercontent.com/72671239/218412912-58de61d1-d5b5-4908-ac35-129482466030.png)

once connected, start inspecting

```bash
find . -type f -size 1033c -readable ! -executable
```

![image](https://user-images.githubusercontent.com/72671239/218417964-4ff358e0-7947-4731-a95a-5f3e5b2b7778.png)

_bandit5 => P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU_

Notes:
[recursive file using find](https://github.com/olaayman999/overthewire/blob/main/bandit/notes/recursive_file.md)
[find command](https://github.com/olaayman999/overthewire/blob/main/bandit/notes/find_file.md)

