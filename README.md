Statlab usage documents
================

# Stat-lab Server

  - hostname: statlab.math.uic.edu
  - Fixed IP address 131.193.178.77

## How to connect to the Statlab Server

  - Shell command `ssh`: [Secure
    Shell](https://en.wikipedia.org/wiki/Secure_Shell)
  - Mac users
      - Terminal.app
      - ssh <username@statlab.math.uic.edu>
          - Follows with your password
  - Windows users
      - PuTTY
      - open source SSH client for
        windows
      - <http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html>

## How to use the R.Studio

  - R
      - Using Terminal or PuTTY
      - Just type `R` in a terminal
  - Rstudio
      - Web browser e.g. Chrome
      - <http://statlab.math.uic.edu:8787/>
  - Some notes about using the Rstudio
      - Save all the documents
      - Save and delete all objects in the Global Environment
        `(rm(list=ls()))`
      - Use top and kill the terminate your R sessions
      - If your Rsutdio freezes, you could use [`killall -u
        USERNAME`](https://linux.die.net/man/1/killall). Note that
        `killall` will only terminate your own processes.
      - Mointor your running script and the usage of the server, you
        could use [`htop`](https://hisham.hm/htop/)

# High Performance Computing (HPC): SABER

  - [Introduction
    slides](https://acer.uic.edu/wp-content/uploads/sites/421/2020/01/Introduction_to_Extreme.pdf)
  - [Basic Knowledge](https://confluence.acer.uic.edu/display/KB/)
      - [Setup SSH
        key](https://confluence.acer.uic.edu/display/KB/Setting+up+SSH+Keys):
        After this setup, you do not need to input your password and
        2-factor code\!

# Github

  - [Github](https://github.com/): For software development version
    control
  - [Education
    pack](https://help.github.com/en/github/teaching-and-learning-with-github-education/about-github-education)
    and unlimited private repositories for FREE\!

## How to use github to version control your projects

1.  Create a [github account](https://github.com/) and linked with your
    uic email
      - Choose the free github account
      - Upgrade your account to the [student
        pack](https://education.github.com/students)
2.  Connect your github account with SSH
      - There is a detailed
        [instruction](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)
        from the github help documents
3.  Create [an empty
    repo](https://help.github.com/en/enterprise/2.13/user/articles/creating-a-new-repository)
    at your github account
4.  Connect your local folder to your github folder:
    1.  Open a terminal and navigate to your local folder, and input
        following commands:
    2.  `git init`: initiate and create the git documents
    3.  `git add .`: add all the modifications to your folder, note `git
        add . -u` is for add all the deleting to your folder
    4.  `git commit -m "first commit"`: commit all the changes to the
        folder
    5.  `git remote add origin git@github.com:username/your_folder`:
        link your local folder to your github folder(only run once)
    6.  `git push -u origin master`: update all the changes to your
        github folder (remote repo)
5.  Now you can
    [copy](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository)
    your github folder to any server you are using

### zsh and github

# tmux

[tmux](https://github.com/tmux/tmux/wiki): It allows multiple terminal
sessions to be accessed simultaneously in a single window. It is useful
for running more than one command-line program at the same time. It can
also be used to detach processes from their controlling terminals,
allowing SSH sessions to remain active without being visible.

![](https://www.perl.com/images/an-introduction-to-tmux/tmux-panes.png)

## How to install tmux

There is a detailed instruction for tmux installation from [this github
page](https://github.com/tmux/tmux/wiki/Installing). The good news is
that `tmux` is available in Statlab server and SABER.

## How to use tmux

1.  There are useful [Getting Started
    documents](https://github.com/tmux/tmux/wiki/Getting-Started) are
    available on its website

2.  The prefix key: `Control - b`. Once a tmux client is attached, any
    keys entered are forwarded to the program running in the active pane
    of the current window. For keys that control tmux itself, a special
    key must be pressed first - this is called the prefix key.

3.  Create a new session: `Control - b` + `c`

4.  Detach from a tmux session: `Control - b` + `d`. Note that, after
    detached from the tmux, you can log out from the server, but your
    script is still running.

5.  Attach a previous tmux session: `tmux attach`

More detailed information of shortcuts can be found in this [cheat
sheet](https://tmuxcheatsheet.com/)

## Configuration

You can customize the layout of your tmux windows by modifying the file
`~/.tmux.conf`. There are so many details of how to configure your tmux,
which is not the focus of this document. But you can find many good
resources online. For example, the [this
one](https://coderwall.com/p/ca5cuw/customize-your-tmux).

# Upload/Downlaod from a server

1.  Terminal:
    [`scp`](https://osxdaily.com/2016/11/07/download-file-from-server-scp-ssh/)
2.  Solftwares:
    [Fetch](https://webstore.illinois.edu/shop/product.aspx?zpid=1244)
    (Free for UIC students, but only for Mac users).
    [Filezilla](https://filezilla-project.org/download.php?platform=win64)
    for windows.
3.  FUSE and sshfs for Mac users

## FUSE (for Mac user only and it requires MacOS \> 10.5)

[FUSE](https://osxfuse.github.io/) allows you to extend macOS’s native
file handling capabilities via third-party file systems. Basically, you
can connect your own Mac with your server’s folder so that you can
upload and download files to the server just as you did locally.

### How to install FUSE and SSHFS

1.  Downlaod and install the `OSXFUSE-{version}.dmg` file from [this
    website](https://osxfuse.github.io/)
2.  Download and install the `SSHFS-{version.pkg}` file from [this
    website](https://osxfuse.github.io/)
3.  Some help documents of
    [FUSE](https://github.com/osxfuse/osxfuse/wiki/FAQ) and
    [SSHFS](https://github.com/osxfuse/osxfuse/wiki/SSHFS)

### How to use SSHFS

After successfully install the FUSE and SSHFS, you are able to connect
the your Mac file system with a server by the following steps: 1. Create
an empty folder in your Mac which will be used to connect the server.
Here, we just name it `mount-point` 1. To connect the server run the
following command: `sshfs username@server:/path-on-server/
~/path-to-mount-point` 1. If everyting is ok, you can find your server
folder in your Mac’s file system
[](%22https://github.com/wal615/Stat-lab-documents/blob/master/SSHFS.png%22)
\# Parallel Computation
