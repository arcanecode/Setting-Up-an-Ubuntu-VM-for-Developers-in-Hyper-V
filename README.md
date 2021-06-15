# Setting Up a Ubuntu VM for Developers in Hyper-V

## Introduction

This suite of instructions was designed to serve as a reminder for yours truly, the humble author. On how to get an Ubuntu virtual machine running and configured in Hyper-V.

Let me be clear, these documents are **not** meant to be a dedicated tutorial. I don't explain a lot of "why's" here, or include screen shots at every step. They are basically a set of reminders on how to do things, what keys to press, buttons to smash, and in what order they should be done.

I find myself setting up new Ubuntu VMs from time to time. Certainly not every day, but often when starting a new Pluralsight course. I've had the instructions for a while, but they were spread out over multiple files in multiple repositories.

I finally decided enough was enough, and set about consolidating all the instructions in one spot. I've organized them in a logical manner, and they are customized for my particular needs, especially when it comes to the software that gets installed.

Also note, some of the configuration decisions were made on the basis of this being installed into a virtual machine, for example disabling screen blanking.

## Valid On

These instructions were written on Windows 10 Pro, the 21H1 version. Ubuntu 20.04 was used for the virtual machine.

For all of the software, we installed the most current versions as of June 14, 2021, the date this repository was created.

## Quick Start vs Using an ISO

In the "create VM" instructions, I used the Hyper-V Quick Start method to download and create an Ubuntu 20.04 Hyper-V installation. This has mixed results. On one hand, it makes installation go quickly and you can be assured you aren't making poor choices. On the other hand, it doesn't provide much opportunity for customization. I do address this however in the instructions, and show how to override some of the default choices before you even start your VM.

Alternatively, you could also create your VM using a downloaded ISO file. My instructions for that can be found at [https://github.com/arcanecode/PowerShellCore/blob/master/Notes/Creating%20an%20Ubuntu%20VM%20in%20Hyper-V.md](https://github.com/arcanecode/PowerShellCore/blob/master/Notes/Creating%20an%20Ubuntu%20VM%20in%20Hyper-V.md).

It was created several years ago when Ubuntu 19.04 was the current version, but except for a few screen shots the instructions are pretty much the same today as they were then. At some point I will wind up copying them into this repository and updating the instructions for the current version of Ubuntu.

## Prerequisites

These instructions presume you are familiar with Hyper-V, as well as Ubuntu. They are designed to let you leverage your knowledge to quickly install Ubuntu in Hyper-V.

## Instructions

Below are a list of the files in this repository, in the order in which they should be followed.

[1-Create-VM-in-HyperV.md](1-Create-VM-in-HyperV.md)

[2-Initial-Ubuntu-Configuration.md](2-Initial-Ubuntu-Configuration.md)

[3-Additional-Configuration.md](3-Additional-Configuration.md)

[4-Install-Software.md](4-Install-Software.md)

[5-Configure-Remoting-on-Ubuntu.md](5-Configure-Remoting-on-Ubuntu.md)

There is also a bonus Quick Reference set of instructions. See it for more information on what it contains.

[Q1-Configure-Git-in-VSCode.md](Q1-Configure-Git-in-VSCode.md)

## The Future

I will update this repository as needed, primarily when a new releases of Ubuntu or Hyper-V will cause the instructions to no longer be valid.

Additionally, they will get updated if I find additional software I feel needs to be added to my base install.

---

## Author Information

### Author

Robert C. Cain | [@ArcaneCode](https://twitter.com/arcanecode) | arcanecode@gmail.com

### Websites

About Me: [http://arcanecode.me](http://arcanecode.me)

Blog: [http://arcanecode.com](http://arcanecode.com)

Github: [http://arcanerepo.com](http://arcanerepo.com)

LinkedIn: [http://arcanecode.in](http://arcanecode.in)

### Copyright Notice

This document is Copyright (c) 2021 Robert C. Cain. All rights reserved.

The code samples herein is for demonstration purposes. No warranty or guarantee is implied or expressly granted.

This document may not be reproduced in whole or in part without the express written consent of the author. Information within can be used within your own projects.
