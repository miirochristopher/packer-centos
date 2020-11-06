# CentOS-7 Minimal Box

This provides the configuration to build a [Vagrant](https://www.vagrantup.com) minimal box using [Packer](https://www.packer.io). The box is intended for server (terminal) use only which allows for a smaller box size.

There is a template provided for the CentOS-7 `x86_64` architecture. 

## Usage Instructions

### Prerequisites

The build environment required is Mac OSX or GNU Linux.

To build the box file you will need the following installed:

- [VirtualBox](https://www.virtualbox.org) (6.1.10)
- [Vagrant](https://www.vagrantup.com) (2.2.10)
- [Packer](https://www.packer.io) (v1.6.5)


### ISO 
It is assumed that you have downloaded the CentOS-7-x86_64-Minimal-2003.iso and placed it in the **packer-centos** directory as **CentOS-7-x64-Minimal.iso**.

Alternatively, you may edit the iso_url in the **CentOS-7-x64.json** which is the packer template file: 

For instance; "iso_url": "http://mirror.ucu.ac.ug/centos/7.8.2003/isos/x86_64/CentOS-7-x86_64-Minimal-2003.iso"

### Build and Run 

1. Clone this repository: 
```
$ git clone https://github.com/miirochristopher/packer-centos.git 
```

2. Go to the root directory. 
```
$ cd packer-centos/
```
3. To build the `x86_64` box, run:
```
$ PACKER_LOG=1 PACKER_LOG_PATH=packer.log packer build CentOS-7-x64.json
```
4. To run the box, run: 
```
$ vagrant up 
```
5. To ssh into the box, run: 
```
$ vagrant ssh
```
