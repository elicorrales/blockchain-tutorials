
## Download The WSL Ubuntu Image  
Go to https://cloud-images.ubuntu.com/releases.  
Scroll and find your desired version.  

[20.04/ 2022-07-12 12:34 - Ubuntu Server 20.04 LTS (Focal Fossa)](https://cloud-images.ubuntu.com/releases/focal/) 

[20.10/ 2022-02-28 16:07 - Ubuntu Server 20.10 (Groovy Gorilla)](https://cloud-images.ubuntu.com/releases/groovy/)  
  
[21.04/ 2022-02-28 16:07 - Ubuntu Server 21.04 (Hirsute Hippo)](https://cloud-images.ubuntu.com/releases/hirsute/)  
  
[21.10/ 2022-07-18 08:19 - Ubuntu Server 21.10 (Impish Indry)](https://cloud-images.ubuntu.com/releases/21.10/)  
  
[22.04/ 2022-07-12 12:51 - Ubuntu Server 22.04 LTS (Jammy Jellyfish)](https://cloud-images.ubuntu.com/releases/22.04/) 
  
## Create The WSL Ubuntu Environment  
  
```
wsl --import <name> "C:\Users\<Windows User>\<VM location Dir name>" C:\Users\<Windows User>\Downloads\ubuntu-(version)-server-cloudimg-amd64-wsl.rootfs.tar.gz
```
  
Example:  
```
wsl --import "21.04.Personal" "C:\Users\EliezerC\21.04.Personal" C:\Users\EliezerC\Downloads\ubuntu-21.04-server-cloudimg-amd64-wsl.rootfs.tar.gz
```

## View The New Ubuntu Environment
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
  
## We Need A Profile Linked To The New Environment  
####  So We Can Easily Select It And Run It  

In Windows Terminal, at top bar, click to view drop-down menu, select  ```Settings```.  
  
At bottom-left, click ```Add a new profile```.  
  
Next, at top-center, click ```New empty profile```.  
  
Enter a name: ```21.04.Personal```.  
  
Enter a command line: ```C:\WINDOWS\system32\wsl.exe -d 21.04.Personal```.  
  
Enter a starting directory: ```~```.  
  
```
NEW_USER=$(cat /etc/wsl.conf|grep default|sed -e 's/^.*default=//');
useradd -m -G sudo -s /bin/bash "$NEW_USER";
passwd "$NEW_USER";
```
  

## To Remove A WSL Ubuntu Environment...  
  
Let's shut down all Ubuntu Environments.
```  
wsl --shutdown
```  
  
Let's lrab/copy the name of the environment we wish to remove.  
```
wsl -l -v
```  
  
We use that name now:  
```
wsl --unregister <distroName>
```
  

