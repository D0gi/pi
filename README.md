# PI

## [Präsentation](https://dog42.github.io/pi)

[ZIP](https://github.com/dog42/pi/archive/master.zip)



# edit raspian.img

- make mountdir `sudo mkdir /media/$USER/bla`
- open img file whit `sudo kpartx -a <raspian.img>`
- mount `sudo mount /dev/mapper/loop0p2 /media/$USER/bla `
- go to mountdir `cd /media/$USER/bla`
- edit content as root and save (may edit `/etc/rc.local` as shown in next step) 
- go out of mountdir `cd`
- `sync`
- umount `sudo umount /media/$USER/bla `
- close img file whit `sudo kpartx -d <raspian.img>`
- `sync`
- rm mountdir `sudo rm -r /media/$USER/bla`


## edit rc.local

add the folowing to `/etc/rc.local` to auto load and run the configfiles on startup:

`wget https://github.com/D0gi/pi/archive/master.zip -O /home/pi/.master.zip`
`unzip /home/pi/.master.zip -d /home/pi/.piconf`
`rm /home/pi/.master.zip`
`./home/pi/.piconf/pi-master/go.sh`


## [Präsentation](https://dog42.github.io/pi)


Also see [MultiPiRemoteControl](https://gitlab.com/jhamfler/MultiPiRemoteControl/tree/master)
