
## Download The WSL Ubuntu Image  
Go to https://cloud-images.ubuntu.com/releases.  
Scroll and find your desired version.  

[20.04/ 2022-07-12 12:34 - Ubuntu Server 20.04 LTS (Focal Fossa)](https://cloud-images.ubuntu.com/releases/focal/) 

[20.10/ 2022-02-28 16:07 - Ubuntu Server 20.10 (Groovy Gorilla)](https://cloud-images.ubuntu.com/releases/groovy/)  
  
[21.04/ 2022-02-28 16:07 - Ubuntu Server 21.04 (Hirsute Hippo)](https://cloud-images.ubuntu.com/releases/hirsute/)  
  
[21.10/ 2022-07-18 08:19 - Ubuntu Server 21.10 (Impish Indry)](https://cloud-images.ubuntu.com/releases/21.10/)  
  
[22.04/ 2022-07-12 12:51 - Ubuntu Server 22.04 LTS (Jammy Jellyfish)](https://cloud-images.ubuntu.com/releases/22.04/) 
  
```
wsl --import <name> "C:\Users\<Windows User>\<VM location Dir name>" C:\Users\<Windows User>\Downloads\ubuntu-(version)-server-cloudimg-amd64-wsl.rootfs.tar.gz
```

```
wsl -l -v
```
OUTPUT:
```
PS C:\Users\EliezerC> wsl -l -v
  NAME                     STATE           VERSION
* Ubuntu                   Stopped         2
  Ubuntu.20.04             Running         2
  21.04.Personal           Stopped         2  <---this is the new one just created
  Personal.Ubuntu.22.04    Stopped         2
PS C:\Users\EliezerC>
```
