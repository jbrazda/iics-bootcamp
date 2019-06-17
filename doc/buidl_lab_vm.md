# Build Ubuntu Based Lab VM

Download [Ubuntu 18.04 LTE Desktop ISO](https://ubuntu.com/download/desktop)

We are using Desktop to install some additional tools useful for Informatica integration development and to simplify setup the labs are described to implement integrations, install secure agent etc on Linux based system.

Create new linux VM `IICS-Ubuntu-18.04 LTE` using downloaded ISO set the drive size to 40 GB, set memory at least to 4GB, for convenience  enable sharing of your home folder with the VM. Set login user as `iclab` and password to your liking.

## Base Installations

Set the Linux VM hostname [follow this guide](https://linuxize.com/post/how-to-change-hostname-on-ubuntu-18-04/)

Run any pending Linux system updates after installation

on shell:

```shell
sudo apt update
sudo apt upgrade
```

Install following packages after Linux system is up to date and started.

```shell
sudo apt install git curl openssh-server ant
```

> I also usually set zsh as my default shell and install ohmyzsh but this is not necessary for your training, see [Installing ZSH](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH)

Additional optional, but very useful packages to install

```shell
sudo apt install mc tig htop pandoc
```

Install Visual Studio Code from [Snap Store](https://snapcraft.io/code) 

```shell
sudo snap install code --classic
```

Install open JDK Java

```shell
sudo apt install openjdk-8-jdk
```

prepare director to install process developer

```shell
sudo mkdir /opt/tools
sudo chown iclab:iclab /opt/tools
```

## Install Informatica Process Developer

Follow instructions in this [guide](https://github.com/jbrazda/Informatica/blob/master/Guides/InformaticaCloud/install_process_developer.md)

Install eclipse to `/opt/tools/eclipse`

Make sure that you create new workspace in `~/workspace/iics`

## Create Directories to Clone Lab Projects

Create folder to clone checkout git repositories in `iclab` user home directory

```shell
mkdir ~/git
```

## Install Docker

We will use Docker in this training to install demo Databases and other components such as Agent monitoring.

Follow this [guide how to install Docker on Ubuntu 18.04](https://linuxize.com/post/how-to-install-and-use-docker-on-ubuntu-18-04/)

## Install Postman

Install Postman via Snap

```shell
sudo snap install postman
```

## Install Secure Agent

### Manual Installation

