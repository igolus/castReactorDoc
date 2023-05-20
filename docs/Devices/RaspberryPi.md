---
sidebar_position: 2
---

# Install Cast reactor on a Raspberry Pi

If you have a Raspberry Pi you can directly install our image.

## How to install cast reactor image

Install the Raspberry Pi Imager from https://www.raspberrypi.com/software/

### Install Raspian Os

Insert a SD card in your computer via USB or card reader

![](/img/rasp1.png)
![](/img/rasp2.png)

- Enable SSH, set your wifi config
- Choose your password

![](/img/rasp3.png)
![](/img/rasp4.png)
![](/img/rasp5.png)

Burn the image on the disk

![](/img/rasp6.png)

### Install Cast Reactor 

Connect with SSH to you pi

![](/img/rasp12.png)

### Update your os

```
sudo apt-get update && sudo apt-get upgrade
```

### Install ansible

```
sudo apt install ansible
```

### Install Cast reactor

```
sudo ansible-pull --extra-vars "user=pi" -v -U https://github.com/igolus/castReactorPi.git
```

### Change Boot option

Change the boot option

![](/img/rasp7.png)
![](/img/rasp8.png)
![](/img/rasp9.png)
![](/img/rasp10.png)
![](/img/rasp11.png)

Reboot and you should see the Cast reactor welcome screen
