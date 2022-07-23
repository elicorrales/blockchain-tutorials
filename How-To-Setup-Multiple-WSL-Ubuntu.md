
## Download The WSL Ubuntu Image  
Go to https://cloud-images.ubuntu.com/releases.  
Scroll and find your desired version.
[DIR] 20.04/                  2022-07-12 12:34    -   Ubuntu Server 20.04 LTS (Focal Fossa) released builds
[DIR] 20.10/                  2022-02-28 16:07    -   Ubuntu Server 20.10 (Groovy Gorilla) released builds [END OF LIFE]
[DIR] 21.04/                  2022-02-28 16:07    -   Ubuntu Server 21.04 (Hirsute Hippo) released builds [END OF LIFE]
[DIR] 21.10/                  2022-07-18 08:19    -   Ubuntu Server 21.10 (Impish Indry) released builds [END OF LIFE - for reference only]
[DIR] 22.04/                  2022-07-12 12:51    -   Ubuntu Server 22.04 LTS (Jammy Jellyfish) released builds
```
wsl --import <name> "C:\Users\<Windows User>\<VM location Dir name>" C:\Users\<Windows User>\Downloads\ubuntu-(version)-server-cloudimg-amd64-wsl.rootfs.tar.gz
```
