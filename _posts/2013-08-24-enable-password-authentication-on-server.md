---
layout: post
title: "enable password authentication on server"
category:
tags:
---
1  SSH into your instance.

2  Edit /etc/ssh/sshd_config and set PasswordAuthentication to yes.

:  One way to do this is to enter the command vi /etc/ssh/sshd_config, then scroll down to PasswordAuthentication.  Press i to go into text insert mode and change the no to yes.  Then press ESC, and type :wq and press enter to save and quit.

3  Enter the command /etc/init.d/sshd reload. (for Ubuntu, enter the command reload ssh)

4  Set your password if you haven't already, with the passwd command.
