username:password => _bandit11 : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM_
                                                                                                                                 
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

![image](https://user-images.githubusercontent.com/72671239/218429028-20dd7338-f0ac-441d-bf82-4c8632ef15ab.png)

```text
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
```
this means that the text have been encoded using rot13, to decode use the following command
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

![image](https://user-images.githubusercontent.com/72671239/218428879-71d347d3-2868-418a-bb4b-a1282b40008f.png)

note that `tr 'A-Za-z' 'N-ZA-Mn-za-m'` is used for both encoding and decoding of rot13

_bandit11 => JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv_
