```
Lesson:     2
Topic:      Package Management and Software Repositories
Type:       Reading
Time:       1 hour
Difficulty: Minimal
```

---
This lesson will cover software, in source, package, and binary form, as well
as how that software is distributed, versioned, updated, and managed. We will
be using the Debian Repositories, as well as the `dpkg` and `apt` tools.

A program, or software is first written in source code form. That program 
cannot be run, or executed, unless it is first compiled. This compilation
converts the text code into machine instructions for the computer.
One challenge that faces compilers is to make machine instructions that work
on *all* computers! This is very difficult to do, and so sometimes an 
intermediary step is included, which is a *package*.

A package is a piece of software that has been compiled, but not yet *customized*
for a particular computer. This packaging allows a company like Mozilla to 
distribute a program like FireFox, and have that program run on most windows
computers, from old XP machines, to brand new Windows 10 machines. The package,
must be *installed* on the computer, using the FireFox package, or installer.

This package form of a piece of software is fairly flexible, and does work, 
however, it requires packages to be made for all of the target operating systems.
For Windows, that is not a problem as a single package is made, however for
Linux, many different packages may have to be made to suite the many different
[distributions](http://en.wikipedia.org/wiki/Linux_distribution).

A program can also be in *binary* form. That is, the program has all ready
be compiled, and can just be run on the computer, without installation.
While this kind of program can be very convent, it is also the most restrictive,
as the machine instructions must work on the majority of computers. If your
computer cannot run the instructions, there is nothing you can do, as the 
program has already been compiled.

---
After software has been installed, or simply run on your computer, it must
be kept up to date. In a Windows environment, it is the job of the program
to check to see if it needs updating, and then to prompt the user to do
updates *for that specific* program.

Additionally, if a program depends on some other program being installed, or
requires that program to be up-to-date, again in a Windows environment, it
is the job of the program to handle the dependencies, and conflicts.

This system, overall results in many different updates, and a large possibility
for programs to conflict with their dependencies.

---
Because the vast majority of Linux programs are
[F/OSS](http://en.wikipedia.org/wiki/Free_and_open-source_software), it is
important that the source code of these programs are available to everyone.
As a result, programs for Linux are typically distributed in source, and
package form. Binary forms of programs are not encouraged because of the
many variations of Linux distributions, and because of the restrictions on
the availability of the source code.

Software packages are maintained in distribution
[repositories](http://en.wikipedia.org/wiki/Software_repository).
Most flavours of Linux use a standard, or perhaps a slightly modified,
software repository.  From there, a single tool, or program is used to fetch
programs from that repository, manage dependencies, and handle update.

There are several different common Linux package formats:
   * .[`deb`](http://en.wikipedia.org/wiki/Deb_%28file_format%29) | Debian Package 
   * .[`rpm`](http://en.wikipedia.org/wiki/RPM_Package_Manager) | Red Hat Package Manager

There are then several different package managers, which use these packages:
   * [`dpkg`](http://en.wikipedia.org/wiki/Dpkg) | a simple package management system for `.deb` packages which does *not* resolve dependencies
   * [`apt`](http://en.wikipedia.org/wiki/Advanced_Packaging_Tool) | a dependency resolution tool that uses `dpkg`, and `.deb` packages
   * [`aptitude`](http://en.wikipedia.org/wiki/Aptitude_%28software%29) | a front-end to `apt`, also using `.deb` packages
   * [`yum`](http://en.wikipedia.org/wiki/Yellowdog_Updater,_Modified) | a package manager which uses `.rpm` packages
   * [`pacman`](http://en.wikipedia.org/wiki/Arch_Linux#Pacman) | Arch Linux package manager


For the purpose of this lesson, we will be looking at the `apt` tool, and how
it uses the Debian package repositories.

---
####Pre-lab questions
Our exploration of `apt` and the other `apt-` tools will continue in the Practical 
portion of this lesson. Before we can start that however, double check that you
are familiar with these ideas:

1. What does the `/etc` folder contain in the [Linux File Structure](http://tldp.org/LDP/intro-linux/html/sect_03_01.html)?

2. Why is it a better idea for a computer system to be managed by a single software downloader/updater?
   How could this idea go wrong?

3. What package formats, and package manager does Ubuntu use?


#####Answers
1. From the [Linux File Structure](http://tldp.org/LDP/intro-linux/html/sect_03_01.html):
>>Most important system configuration files are in /etc, this directory contains data similar to those in the Control Panel in Windows

2. One updater means a single thing to update the whole system. Inner conflict are easily avoided, since the package manager can track the dependencies for each program
   If the package manager is corrupted, it may be difficult to fix, as it is responsible for download/updating software.
   Additionally, the package manager cannot track software that was installed on the system without the use of the package manager.

3. Ubuntu uses the `.deb` package formats, along with `dkpg`, `apt`, and `aptitude`.

