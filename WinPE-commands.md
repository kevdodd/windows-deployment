## Create WinPE files
* copype amd64 C:\WinPE_amd64

## Create WinPE USB bootable disk where F: is the USB drive
* MakeWinPEMedia /UFD C:\WinPE_amd64 F:

## Mount WinPE boot.wim file to customize 
* Dism /Mount-Image /ImageFile:"C:\WinPE_amd64\media\sources\boot.wim" /index:1 /MountDir:"C:\WinPE_amd64\mount"

## Unmount the WinPE image and commit changes
* Dism /Unmount-Image /MountDir:"C:\WinPE_amd64\mount" /commit
