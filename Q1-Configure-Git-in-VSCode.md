# Quick Reference - Configure Git in VSCode

## Introduction

In step 3 of these instructions, we cover installing GIT and configuring it with your user ID.

In order to cache your credentials, you have to have either downloaded a project from GitHub, or created a new VSCode project stored in GIT. Only then can you cache your credentials, so you don't have to login every time you want to push your project to GIT / GitHub.

While the how to was explained in file 3, it is likely you may need to refer back to them at least once, possibly more, so I've recreated them here for your quick reference.

# Preliminary - GIT Installation and Initial Configuration

Hopefully you followed the instructions in [3-Additional-Configuration.md](3-Additional-Configuration.md), and installed GIT, then configured it with your name and email address. If not here it is again as a reminder.

First, install GIT.

```bash
sudo apt -y install git-all
```

GIT is pretty big so it may take a while.

Once installed, we'll configure GIT with our user name and ID.

```bash
git config --global user.name "Robert Cain"
git config --global user.email arcanecode@gmail.computer
```

# Configure GIT for Your VSCode Project

So now you have a VSCode project open, and want to get it into GitHub. The simplest way to create a new project is actually in GitHub.

Go to you GitHub account, and create a new repository. Let it create a ReadMe.md file for you, and if you want pick a license for your repository.

Once the project exists, go to VSCode, and use the **Clone Git Repository** feature. Give it the URL to your new repository.

You will then be prompted to give your credentials. It will take you to GitHub where you'll be asked to login, then confirm you want to let VSCode access your repository.

> _Hint: It will go much easier if you first login to your GitHub site in your default browser._

So now you have your project downloaded and in VSCode.

In the bash terminal within VSCode, you can first indicate the place to store the credentials.

```bash
git config credential.helper store
```

Then you'll want to add the current project to git so it can use the stored credentials.

```bash
git push https://your-github-project-here.com
```

When you enter this command, git opens your browser and attempts to log you into your GITHUB site (yes, again). Once it does, it will ask you to confirm it's OK for VSCode to access your repository.

From here on out, you should be able to make changes, commit them to your local GIT repository, then once committed push them to your GitHub site, all within VSCode and without having to login every time.
