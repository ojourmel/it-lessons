```
Lesson:     2
Topic:      Package Management and Software Repositories
Type:       Lab
Time:       1 hour
Difficulty: Moderate
```

---
In this lab, we will practise searching for, installing, and modifying
several different packages via a package manager. We will also be looking
at the configuration files that the package manager `apt` uses.
It is recommended that you take a [snapshot](http://www.virtualbox.org/manual/ch01.html#snapshots)
_before_ you begin this lab.

####Lab resources
The _man_, or _manual_ pages for `apt` and the related tools will be useful.
You can view them in a terminal by typing: `man apt` or `man apt-get`.
Additionally, the resources are available online:
   * [`apt`](http://linux.die.net/man/8/apt)
   * [`apt-get`](http://linux.die.net/man/8/apt-get)
   * [`apt-cache`](http://linux.die.net/man/8/apt-cache)


####Task List
* Update and Upgrade your system from the command line using `apt-get`
   * `sudo apt-get update`
   * `sudo apt-get upgrade`
* Search for all packages containing the word `git`
   * `sudo apt-cache search git`
* Install `git`
   * `sudo apt-get install git`
* Backup the `apt` sources file
   * `sudo cp /etc/apt/sources.list /etc/apt/sources.list.old
* Remove all sources from the `apt` sources file
   * `sudo gedit /etc/apt/sources.list`
* Update the system, and then search for, and install an application, like `vlc`
   * `sudo apt-get update`
   * `sudo apt-cache search vlc`
   * `sudo apt-get install vlc`
* Restore the old `apt` sources file, and try again.
   * `sudo cp /etc/apt/sources.list.old /etc/apt/sources.list`
   * `sudo apt-get update`
   * `sudo apt-get install vlc`


####Task Notes:
As was discussed in the Theory, there are several different package managers
used in Debain. `dpkg` is the origonal tool, which simply installes package.
`apt`, and the `apt-get` tools handle dependencies, and use `dpkg`. 
`aptitude` is also a front end for `dpkg` and the `apt` tools. Finaly, 
`The Software Centre` is also a front end for `dpgk`. In this lab,
we will be using the `apt` tools. `aptitude` is also a very good tool to use,
but can be a bit difficult to navigate.

Play around with the items in the Task List. You may find that some searches
return a large amount of text, and it is nessisary to scroll back. You can
also [pipe](http://www.ibm.com/developerworks/library/l-lpic1-v3-103-4/) the
output of a command to another program. This is used to "save" the results.
Here, a command which will produce a lot of text can be piped to [less](http://linux.die.net/man/1/less).
* `sudo apt-cache search git | less`.
Less is a file viewer. Use the `j`, or `down` arrow keys to move down, and the
`k` or `up` arrow keys to move up. Simply type `q` to exit.

What happendes in the lab when you remove all of the sources from the `apt`
sources list? What would happen if one of the servers listed in the `sources`
file went off-line?

While some of the intrecisies of package managers are not delt with in this
lab, the basics needed to explore the packages are.

If you are looking for a tool, or program, first search for it using `apt-cache`.
The descriptions of programs are included in the search, so this is a reasonalbe command:
* `sudo apt-cache search morse code`
If that does not return anything worthwhile, a quick google search may point
you in the direction of the tool you are looking for. From there, search
for that tool in the respositories. If that does not work, there may be
a packaged version of the tool, not hosted in the default repositories.

Single software packages can be downloaded and installed using `dpkg`. Assumeing
you have download a package called `simple-software-3.02.deb`, install in
by typing: `sudo dpkg --install simple-software-3.02.deb` in the same directory.

Finaly, if a piece of software is not in the repositoes, or avaleble from a 
third party, you man need to download the source code, and build the software
yourself. This process is much more involed, and we shall leave it for another
time.


####Post-lab questions
1. If an attacker was able to gain acess to your `/etc/apt/sources.list` file,
   what could they do with it?
2. Is there only ever one version of a software avalible for download? How
   does the package manager decide which ones to download/install?
3. By using dependencies, a piece of software can have alot of influence over
   what kinds of tools are installed on your system. How could that be 
   problimatic?
4. What is the difference between `apt-get update` and `apt-get upgrade`?
5. What is the difference between `apt-get upgrade` and `apt-get dist-upgrade`?

#####Answers
1. An attacker could direct your package manager to a false repository, where
   "bad" versions of software could be installed on your computer. One way this
   is avoided in the current system is by providing a [checksum](http://en.wikipedia.org/wiki/Checksum)
   or hash of the software, to garentie that you have recived the correct package.
2. There are often multiple different versions of a software to download. The
   package manager uses the most recient version, which does not interfrer with
   other programs. The version to be installed *can* be manualy specified.
3. One developer could require that all his or her other software be installed
   in order for one *critical* tool to work properly.
4. `apt-get update` simply gets the list of all the software avalible to install.
   This "updates" your `apt` database. `apt-get upgrade` does a full system "upgrade",
   installing all new versions of software that can be safley installed.
5. `apt-get dist-upgrade` is a "distribution" upgrade, and is used to upgrade
   the more vital parts of your system, like the [kernel](http://en.wikipedia.org/wiki/Linux_kernel).
