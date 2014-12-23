```
Lesson:     1
Topic:      **Virtualization and Virtual Box**
Type:       Lab
Time:       2 hours
Difficulty: Moderate
```

---
In this lab, we will install VirtualBox on a host computer, and create a new
virtual machine. We will play around with VirtualBox configuration, and
install [Debian](https://www.debian.org/) on a virtual machine. This Debian
install will be used throughout the lessons. Other virtual machines can
be created, and deleted without affecting the Debian install.

####Lab resources
VirtualBox has a very good [Manual](http://www.virtualbox.org/manual/ch01.html).
Additionally, there are specific resources for [creating new virtual machines](http://docs.oracle.com/cd/E26217_01/E26796/html/qs-create-vm.html). 


####Task List
* Install VirtualBox ([Download Link](https://www.virtualbox.org/wiki/Downloads))
* Create a new virtual machine
   * Create a new HDD, of at least `30GB`
   * Enable `Use Host I/O Caching`. This is done *after* the virtual machine
      has been created. Right click the machine name, and select `Settings`.
      Under `Storage`, there is a check box for `Host I/O Caching`. Ensure this
      checkbox is checked.
* Download Debian ([Download Link](http://cdimage.debian.org/debian-cd/7.7.0/i386/iso-cd/debian-7.7.0-i386-netinst.iso)
* "Insert" the Debian `ISO` into the virtual machines CD-ROM
   * Go to machine settings, and then `Storage`. From there, select the IDE
      device, and tick `Bootable Mediam` checkbox. Select the small folder 
      icon, to select the `ISO` that should be used.
* Install Debian on the virtual machine
   * `Hostname` refers to the computer name
   * Use default mirror lists
   * Do *NOT* set a `root` password (leave it blank); use the user account password with `sudo`
   * Install the base system, and the Graphical User Interface (Gnome) if prompted
   * Do not set a proxy
   * Use `Guided Partitioning`, and default full disk
* Remove the Debian ISO from the virtual machine


####Task Notes:
There are two key goals of this lab. The first is to familiarize yourself with
VirtualBox, and the virtual machine settings. The second is to install
Debian on a virtual machine, which will be used later in the lessons.

The *first* point is the important one, so if this lab needs to be split
into two sessions, that is acceptable. First install VirtualBox, and familiarize
yourself with creating new machines, and changing all the settings within
those machines. The default values are acceptable, however, play around with
the amount of RAM, the number of CPUs, and other settings.

The second point is a simple application of creating and Virtual machine,
using Debian as the operating system. Installing Debian can be a long 
process by itself, and must be completed from start to finish. Allocate
enough time before starting the install process.


####Post-lab questions
1. Is is possible to create a virtual machine with no Internet access?
2. Is it possible to create a virtual machine with more than one CPU?
3. Is it possible to give a virtual machine more CPUs than exist on the host computer?
4. Why could the Debian installer use a text-based install screen.
   Why not a fancy GUI?

#####Answers
<sup>
1. Yes. Go to `Networking`, and remove the virtual adaptor
2. Yes, if the host computer has more than one CPU core.
3. No. The virtual machine is limited to the hardware of the host computer.
4. Because it is simpler, faster, and easier to make a text-based install. 
</sup>



