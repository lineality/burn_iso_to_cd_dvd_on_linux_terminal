# burn_iso_to_cd_dvd_on_linux_terminal

(works on fedora running on dell laptop running generic cheap USB cd burner by LG)

#### Source for method: https://www.cyberciti.biz/faq/linux-burn-iso-images-to-cds-and-cd-rws-howto/

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

Run:
```
$ cdrskin --version
```
Example output:
```
install cdrskin
```

Run:
```
$ cdrecord -scanbus
```
Example output:
```
scsibus0: 0,0,0
```

Format:
```
cdrecord -v -dao dev=NUMBER,NUMBER,NUMBER speed=NUMBER /YOUR/FILE_PATH.iso
```


Examples of iso burn terminal run instructions:
```
$ cdrecord -v -dao dev=0,0,0 speed=2 /home/xxx/Downloads/install51.iso

$ cdrecord -v -dao dev=0,0,0 speed=2 /home/xxx/Downloads/FreeBSD-11.2-RELEASE-i386-disc1.iso

$ cdrecord -v -dao dev=0,0,0 speed=2 /home/xxx/Downloads/5.2.1-RELEASE-i386-disc1.iso

$ cdrecord -v -dao dev=0,0,0 speed=2 /home/oops/Downloads/5.2.1-RELEASE-i386-disc2.iso
```

