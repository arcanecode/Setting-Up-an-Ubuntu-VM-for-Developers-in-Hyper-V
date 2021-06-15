# Additional configurations

In this document, you'll see how to apply some system configurations to make Ubuntu work as a developers VM. We'll disable things like sleep and suspend, install a basic editor, and set our default screen size.

## Install VIM, a basic editor for the Terminal

We'll need a decent text based editor we can call from the command line to edit some Ubuntu configuration files. VIM is popular and easy, so we'll install it.

```bash
sudo apt install vim
```

## Disable Sleep and Suspend

There's no real reason we need our VM to sleep, or suspend. We should disable these.

```bash
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```

If it was successful, you should see:

```bash
Created symlink /etc/systemd/system/sleep.target --> /dev/null.
Created symlink /etc/systemd/system/suspend.target --> /dev/null.
Created symlink /etc/systemd/system/hibernate.target --> /dev/null.
Created symlink /etc/systemd/system/hybrid-sleep.target --> /dev/null.
```

Note you will then have to reboot the VM for these to take affect, but we can first set the screen size and timeout, as we'll see in the next section.

## Set Screen Timeout and Screen Size

Ubuntu defaults to an annoyingly short amount of time before the screen blanks. In a VM we can set it to never go blank, since we can rely on the host operating system to go blank according to your preferences.

At the same time, we can also set the default screen size we want to use. In my case we'll pick 1920x1080, but pick what works best for you.

In the terminal, open `/etc/default/grub' in your newly installed VIM editor.

```bash
sudo vim /etc/default/grub
```

Now find the line that begins with `GRUB_CMDLINE_LINUX_DEFAULT`. Hit the letter **I** to begin insert mode.

At the end of the line, we'll first append `consoleblank=0`.

Next, we'll add the video size. `video=hyperv_fb:1920x1080`

The final line should look like:

```bash
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash consoleblank=0 video=hyperv_fb:1920x1080"
```

Now find the line that reads `GRUB_CMDLINE_LINUX=""`. It is usually the next line.

Alter it to read:

```bash
GRUB_CMDLINE_LINUX="video=hyperv_fb:1920x1080"
```

Now save the changes by hitting **ESC :wq**

The escape key will exit insert mode, w will write (aka save) the file, and q will quit VIM. Note if you didn't remember to use `sudo` at the beginning of the command to launch VIM, you'll get an error that you don't have permission to write the file.

This next step is **very important**!! You must update grub for our changes to work!

```bash
sudo update-grub
```

## Set Power Saving Blank Screen Time

Finally, we'll disable Ubuntu's annoying habit of going blank after five minutes. Enter the Ubuntu menu, then open **Settings**

Navigate to **Power** on the left.

Use the drop down menu by _Blank Screen_ and set it to **Never**

## Time to reboot

Now we are ready to reboot. And by reboot, I mean do a shut down, then restart the VM in Hyper-V.

You could of course use the menus, but since we are already at the command line we'll use:

```bash
sudo /sbin/shutdown now
```

Once, done, return to Hyper-V and start the machine.

## Next Steps

With your machine rebooted, it's time to install some software. You'll find those instructions in our next file, [4-Install-Software.md](4-Install-Software.md).

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
