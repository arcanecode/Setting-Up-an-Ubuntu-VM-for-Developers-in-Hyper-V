# Install Software

Next we will be installing useful software packages. These are the general set of packages I like to have in my VM, but you should choose the software you need.

## Network Tools

The network tools are a useful group of utilities for getting things like the IP address of your computer.

```bash
sudo apt -y install net-tools
```

You can test the install using `ifconfig` command at the terminal.

## Install GCC

The gcc, g++, and make utilities are used by a lot of third party tools, so lets get them installed.

To install all three at once, we can use:

```bash
sudo apt -y install build-essential
```

It might also be useful to have the documentation for these tools, so next run:

```bash
sudo apt-get install manpages-dev
```

We can test the install by running `gcc --version` to see what version of gcc was installed.

## Install and Configure GIT

For any type of development we'll need source control. In this VM we'll install GIT.

```bash
sudo apt -y install git-all
```

GIT is pretty big so it may take a while.

Now we'll configure GIT. First we'll add our user name and ID.

```bash
git config --global user.name "Robert Cain"
git config --global user.email arcanecode@gmail.computer
```

Later, once you open a project in VS Code from GIT, you'll be able to store your credentials so remember these instructions when it is time. 

In the bash terminal within VSCode, you can first indicate the place to store the credentials.

```bash
git config credential.helper store
```

Then you'll want to add the current project to git so it can use the stored credentials.

```bash
git push https://your-github-project-here.com
```

When you enter this command, git opens your browser and attempts to log you into your GITHUB site. Once it does, it will ask you to confirm it's OK for VSCode to access your repository.

Here's a time saving hint, open your browser and login to github first. I've found it makes the process go quicker and is less error prone.

Note that we have saved a copy of these instructions in the file [Q1-Configure-Git-in-VSCode.md](Q1-Configure-Git-in-VSCode.md). This will make it much easier for you to locate once you start working in VSCode.

## Install PowerShell

Next we will install PowerShell using a snap. In the terminal:

```bash
sudo snap install powershell --classic
```

The `--classic` is needed to allow PowerShell to interact with the system.

Once installed you can test by entering `pwsh` in the terminal to start a PowerShell session. You can further test by entering a PowerShell command such as `Get-Help`, or `$PSVersionTable`.

When done just use `exit` to leave PowerShell and return to the normal terminal.

## Install VSCode

Next we'll install VSCode.

```bash
sudo snap install code --classic
```

That's it, pretty simple.

## Install Azure Data Studio

Prior to installing ADS, you should make sure you have a file it depends on.

```bash
sudo apt-get install -y libunwind8
```

Unfortunately there is no snap installer for Azure Data Studio. You'll need to go to the Azure Data Studio site and download the .deb installer.

[https://docs.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-ver15](https://docs.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-ver15)

Alternatively you can open FireFox and enter `azure data studio download for ubuntu` as the search term, the page should come right up.

Use the _Version_ drop down in the upper left to pick the version you need. The page has detailed instructions on how to install on your OS.

Once downloaded, in the terminal move to your downloads folder with `cd Downloads`.

Install using the following command:

```bash
sudo dpkg -i azuredatastudio-linux-<version>.deb
```

Replacing <version> with the version of the file downloaded.

## Configure the Ubuntu Desktop Favorites Bar

When you install Ubuntu in a VM over and over, to setup either classroom or dev environments, you may want to automate the process of setting up your "favorites" bar on the left side of the display.

If you want to see what the current set of favorites are, use:

```bash
/usr/bin/gsettings get org.gnome.shell favorite-apps
```

The easiest way to determine your favorites list is to manually configure it once, adding and removing what you want. Then run the above command again, to get the list of your favorites. Copy and paste the output, and pass it into the `gsettings -set` command.

I use the following command to set mine, yours of course will reflect which favorites you want handy.

```bash
gsettings set org.gnome.shell favorite-apps "['firefox.desktop', 'org.gnome.Terminal.desktop', 'org.gnome.Nautilus.desktop', 'code_code.desktop', 'azuredatastudio.desktop', 'org.gnome.Software.desktop', 'yelp.desktop']"
```

## Final Steps - Run software updates

As a final step, you should let Ubuntu go through and update all the software. In the Ubuntu menu, open the Software Updater. Then, let it do its thing.

Finally, you should go ahead and open VSCode and login to it. If you are using the new account sync functionality, and you chose GitHub as the syncing location, it will need to authenticate via GitHub. Go ahead and be sure you are logged in to GitHub on your default browser, it will make the process easier and faster.

## Optional - Configure Remoting

If you will need to SSH _into_ this virtual machine, or _from_ this VM, then you should proceed to the instructions found in [5-Configure-Remoting-on-Ubuntu.md](5-Configure-Remoting-on-Ubuntu.md).

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
