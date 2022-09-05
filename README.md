## burn_iso_to_cd_dvd_on_linux_terminal

#### Source for method: https://www.cyberciti.biz/faq/linux-burn-iso-images-to-cds-and-cd-rws-howto/

# Instructions 
To burn an iso/img to a CD or DVD disk on linux via command line terminal
(works on fedora running on generic laptop running generic cheap USB cd burner)

Run: see what you have installed. OS with either say: you have what you need, or it will tell you what standard and available packages you should install:
```
$ cdrecord --version
```
Example output:
```
bash: cdrecord: command not found...
Packages providing this file are:
'cdrskin'
'wodim'
'xorriso'
```

Run: A clean way to check and install is run --version for a package, and let the os ask you if you want to install it. Say 'y' (yes)
```
$ cdrskin --version
```
Example output:
```
~ Not found... do you want to install cdrskin? (y, N)
```

#### Say 'y' (yes)

Run: Find out what the 3-number address is for your cd burner.
```
$ cdrecord -scanbus
```
Example output:
```
scsibus0: 0,0,0
```

Put the above three numbers into the "NUMBER,NUMBER,NUMBER" part of the format below (see examples below-below), as well as your iso file path and the burn-speed (2-8?) Note: faster may be error prone.

Run: Put your information into the following command to burn the disk.

Format:
```
cdrecord -v -dao dev=NUMBER,NUMBER,NUMBER speed=NUMBER /YOUR/FILE_PATH.iso
```


Examples of iso burn terminal run instructions:
```
$ cdrecord -v -dao dev=0,0,0 speed=2 /home/xxx/Downloads/install51.iso

$ cdrecord -v -dao dev=0,0,0 speed=2 /home/xxx/Downloads/FreeBSD-11.2-RELEASE-i386-disc1.iso

$ cdrecord -v -dao dev=0,0,0 speed=2 /home/xxx/Downloads/5.2.1-RELEASE-i386-disc1.iso

$ cdrecord -v -dao dev=0,0,0 speed=2 /home/xxx/Downloads/5.2.1-RELEASE-i386-disc2.iso
```


