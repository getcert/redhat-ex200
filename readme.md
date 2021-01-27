
<p align="center">
  <img width="22%" src="https://res.cloudinary.com/dkmuc5wf9/image/upload/v1611592207/getcert-brand/image-01_b0sbwl.svg" align="center" alt="GetCert " />
  <h1 align="center">Red Hat - EX200</h1>
  <p align="center">The skills tested in this exam are the foundation for system administration across all Red Hat® products.</p>
  <p align="center">For details and how to use this repo please visit the <a href="https://getcert.org/getting-started">Getting Started</a> page.
  <br />
  <p align="center">
    <a href="https://github.com/getcert/redhat-ex200/stargazers">
      <img alt="Stars" src="https://img.shields.io/github/stars/getcert/redhat-ex200?color=75AADB" />
    </a>
    <a href="https://github.com/getcert/redhat-ex200/network/members">
      <img alt="Forks" src="https://img.shields.io/github/forks/getcert/redhat-ex200?color=75AADB" />
    </a>
    <a href="https://github.com/getcert/redhat-ex200/blob/main/LICENSE">
      <img alt="License" src="https://img.shields.io/github/license/getcert/redhat-ex200" />
    </a>
  </p>
</p>

---

#  

# Flashcards

![](repo-img/redhat-ex200-flashcards.png)

# Playlists


# Playground

## VirtualBox flavor.

>  `cd playground/virtualbox/` and follow this guide

### Requirement

>  +  Vagrant
>  +  VirtualBox
>  +  2CPU cores
>  +  5GB of local RAM

### Plugins

>  Please first install this plugins:

```
vagrant plugin install vagrant-hostmanager
vagrant plugin install vagrant-vbguest
```

### Usage

>  First time it take around 30 min for setup and make essential configurations
>>  Next time vagrant need just a few seconds... 

```

# ignition! this command setup or turn on all the machines

vagrant up

# if you make some change on the extras files, to apply it use the flag --provission

vagrant up --provision

######### the prompt ask you for chose the bridge interface, common cases use **eth0** or the firs available real interface.

######### put the number of your interface and hit enter.

1) eth0
2) docker0
    bastion: Which interface should the network bridge to? 1

#########
```


### Useful vagrant commands:
> to avoid re-provision over and over again when you want start from a clean instance use `snapshot save` the first time you deploy the lab and `snaphost restore` every single time you want a fresh and quick instance.

```
vagrant destroy -f - Shuts down and destroys the environment
vagrant halt - Shuts down the environment VMs (can be booted up with vagrant up)
vagrant suspend - Puts the VMs in a suspended state
vagrant resume - Takes VMs out of a suspended state

# first time you have the lab up and running save it with a snapshot
vagrant snapshot save base-00

# to list all the saved snapshot
vagrant snapshot list

# to restore a snapshot
vagrant snapshot restore base-00
```


### Synced folder between HOST (your machine) and GUEST (workstation)

```
   HOST                     GUEST
./synced ←←← →→→ /home/student/synced
```

### vagrant --version

> Vagrant 2.2.14

### vboxmanage --version

> 6.1.16

### topology

```
172.25.250.254    bastion        bastion.lab.example.com

172.25.250.9      workstation    workstation.lab.example.com
172.25.250.10     servera        servera.lab.example.com
172.25.250.11     serverb        serverb.lab.example.com

192.168.1.222     ·······        use this ip for LAN access 
```

### VBox List
```
VBoxManage list runningvms
   "bastion" {ecb55eeb-7de3-4ecc-a812-71b29fb1c89f}
   "workstation" {9683fabe-2332-4439-9534-76ec40e66a81}
   "servera" {13ff8c3f-334d-48e8-aba9-c923149b7eb7}
   "serverb" {8598bea6-10be-4470-9d9e-140acca0cac8}
```

### default credentials

```
user: root
pass: redhat

user: student
pass: student
```
