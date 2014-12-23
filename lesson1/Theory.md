```
Lesson:     1
Topic:      **Virtualization and Virtual Box**
Type:       Reading
Time:       1 hour
Difficulty: Minimal
```

---
Virtualization is the emulation of hardware with software. While it can take
on many forms, computer virtualization can be used to run complete,
[sandboxed](http://en.wikipedia.org/wiki/Sandbox_%28computer_security%29) environment.

For the purpose of this lesson, we will be looking at [VirtualBox](https://www.virtualbox.org/), 
which is a popular open source virtualization software. VirtualBox can be 
installed on Windows, Mac, and Linux computers, and can be used to create
an environment for most popular operating systems.

VirtualBox, and virtualization will be used throughout these lessons to
provide a playground for the labs, as well as, provide a safe environment
where mistakes can be made, without jeopardizing the real computer.

This lesson, we will also cover [RFCs](http://en.wikipedia.org/wiki/Request_for_Comments),
and some 


Before preceding to the lab, read, and familiarize yourself with the following
topics. Note that some articles contain *excessive* amounts of information.
   * [Virtualization](http://en.wikipedia.org/wiki/Virtualization)
   * [NAT](http://en.wikipedia.org/wiki/Network_address_translation)
   * [RFC](http://en.wikipedia.org/wiki/Request_for_Comments)
   * [GUI](http://en.wikipedia.org/wiki/Graphical_user_interface)


####Pre-lab questions
1. A common example of virtualization is [Virtual Private Servers](http://en.wikipedia.org/wiki/Virtual_private_server).
   These servers are used for many things on the Internet. Why might it
   be beneficial for companies to own a single, super computer, and then
   visualizer servers, instead of simply running many "real" servers?

2. NAT can be used to connect a computer to a larger network, without exposing
   that computer to the larger network. Why might this be important?

3. Why where RFCs important to the development of the Internet?
   Why are we still interested in them today?


#####Answers
<sup>
1. It is simpler to support a single computer, than many thousand computers.
   It is easier to create a virtual computer than it is to pull a server off
   a shelf and plug it in. It is *much* simpler to install an operating 
   system on a virtual machine, as a template machine can be used. If a 
   virtual server is not being used, the resources normally allocated for that
   virtual machine can be used elsewhere.

2. If the computer can talk to the larger network, but the larger network has
   difficult initiating contact back, this isolates the computer, and can
   prevent direct attacks, all while still allowing the computer to use
   the larger network.

3. Because the Internet was developed, and created using many different peoples
   ideas and expertize, it is important for those people to communicate their 
   ideas. One of the simplest forms of group communication is a mailing list.
   RFCs are a way of presenting a topic, often on a mailing list, and allowing
   others to give input on the issue. RFCs also maintain a record of many
   of the ideas surrounding the Internet, and will be referenced many times
   throughout these lessons.
</sup>
