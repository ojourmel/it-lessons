```
Lesson:     1
Topic:      Virtualization and Virtual Box
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
* Download Debian ([Download Link](http://cdimage.debian.org/debian-cd/7.7.0/i386/iso-cd/debian-7.7.0-i386-netinst.iso))
* "Insert" the Debian `ISO` into the virtual machines CD-ROM
   * Go to machine settings, and then `Storage`. From there, select the IDE
      device, and tick `Bootable Mediam` checkbox. Select the small folder
      icon, to select the `ISO` that should be used.
   * ![This](http://cdn4.groovypost.com/wp-content/uploads/2011/09/image54.png) image may be useful
* Install Debian on the virtual machine
   * Select a graphical install
   * `Hostname` refers to the computer name
   * Use default mirror lists
   * Do *NOT* set a `root` password (leave it blank); use the user account password with `sudo`
   * Install the base system, and the Graphical User Interface (Gnome) if prompted
   * Do not set a proxy
   * Use `Guided Partitioning`, and default full disk
   * Install the boot loader, `grub` to `/dev/sda` (default).
* Remove the Debian ISO from the virtual machine
   * Go back to machine settings, then Storage, and remove the disk from the virtual "CD-ROM"


####Task Notes:
There are two key goals of this lab. The first is to familiarize yourself with
VirtualBox, and the virtual machine settings. The second is to install
Debian on a virtual machine, which will be used later in the lessons.

The *first* point is the important one, so if this lab needs to be split
into two sessions, that is acceptable. First install VirtualBox, and familiarize
yourself with creating new machines, and changing all the settings within
those machines. The default values are acceptable, however, play around with
the amount of RAM, the number of CPUs, and other settings. If there are any
acronyms that don't make sense, like `PAE/NX`, search them in Wikipedia, to
get an idea of what they do.

Taken directly from the [Wikipage](http://en.wikipedia.org/wiki/Physical_Address_Extension):
> In computing, Physical Address Extension (PAE) is a feature to allow 32-bit
> IA-32 central processing units (CPUs) to access a physical address space
> (including random access memory and memory mapped devices) larger than
> 4 gigabytes.

The second point is a simple application of creating and virtual machine,
using Debian as the operating system. Installing Debian can be a long
process by itself, and must be completed from start to finish. Allocate
enough time before starting the install process.


####Post-lab questions
1. Is is possible to create a virtual machine with no Internet access?
2. Is it possible to create a virtual machine with more than one CPU?
3. Is it possible to give a virtual machine more CPUs than exist on the host computer?
4. Why could the Debian installer use a text-based install screen.
   Why not a fancy GUI?
5. Does it matter if there are multiple virtual machines on one host?
6. Does it matter if multiple virtual machines are all running at once?

#####Answers
1. Yes. Go to machines settings, and `Networking`, and remove the virtual adaptor
2. Yes, if the host computer has more than one CPU core.
3. No. The virtual machine is limited to the hardware of the host computer.
4. Because it is simpler, faster, and easier to make a text-based install.
5. No. You can have as many machines as you want.
6. Yes. If many virtual machines are running, the host computer, may have trouble
   keeping up, and things may slow down. One of the things that you will run out
   of first is RAM. Watch RAM usage on the host computer when you start multiple
   virtual machines.



