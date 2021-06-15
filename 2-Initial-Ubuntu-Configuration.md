# Initial Ubuntu Configuration

When you start the Ubuntu virtual machine for the first time, you'll be presented with the GRUB menu. Just take the default of Ubuntu and keep going.

You are now going to be stepped through the system configuration. Since there are hundreds of tutorials, videos, and the like already on the web, I'm not going take space explaining things you likely have done before.

Instead, I'll just list the screen number, title, and what you should pick.

## Screen 1: System Configuration, Language

Pick your language (English in my case) then click Continue

## Screen 2: Keyboard Layout

I use English (US), but you pick what is your proper setting, then click Continue.

## Screen 3: Time Zone

Select a city in your time zone. In my case I'm in central time zone, so will pick Chicago and click Continue.

## Screen 4: User Name and Computer Name

Enter your name, with spaces, such as: `Arcane Code`

Enter your computer name. I like to include VM in the tile so if I ever do a network scan I can easily identify my VMs. I'll use: `ac-ubuntu-20-04-vm`

Now pick a user name, for me it'll be `arcanecode`. I suggest all lower case, it will make it easier if you are having to navigate your user folders from the command line.

Then enter, and re-enter a password. No, I'm not going to tell you what mine is.

Finally make sure **Require my password to log in** is selected, and click Continue.

Now kick back and wait for Ubuntu to do its system configuration.

## First Boot

After configuration the VM will reboot, and you'll be prompted to log in. Do so.

Ubuntu will now prompt you to connect your online accounts. If this were a pure hardware install that might be nice, but in a VM it's not likely you'll need these services so just click **Skip**.

Next you are asked about Livepatch, a service that lets you apply security updates without the need to reboot. Many times though, you want to keep your Ubuntu VM at a certain release, to match your corporate environment. We'll assume that is the case here and click **Next**. Just be aware that you'll need to apply updates yourself and reboot after them.

Now you are asked if you want to send metrics to help improve Ubuntu. When I install Ubuntu on a physical computer I turn this on. However being a VM I don't think it will give an accurate reflection of normal Ubuntu usage, so I turn this off by clicking **No, don't send system info** then hitting **Next**.

The next screen asks if you want to turn on Location Services. Unless my VM will be doing something with geographic data, I leave this off and click **Next**.

Finally you are asked about installing software. We'll do much of this via the command line, so just click **Done**.

## Update Ubuntu 20.04

The final step in your initial boot should be updating Ubuntu.

Start by opening a Terminal window. You can find it in the menus, or use the CTRL+ALT+T keyboard shortcut.

Next, apply updates.

```bash
sudo apt update
```

Once that is done, you will want to upgrade any packages to the latest version.

```bash
sudo apt upgrade
```

Note this does not upgrade Ubuntu itself, for example going from 20.04 to 21.04. It just brings all the built in packages up to their latest releases.

## Next Steps

With your initial boot complete, and system updated, it's time to apply some additional configurations to customize Ubuntu for our needs. We'll do that in the next file, [3-Additional-Configuration.md](3-Additional-Configuration.md).

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
