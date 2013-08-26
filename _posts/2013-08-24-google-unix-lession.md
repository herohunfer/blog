---
layout: post
title: "Google Unix Lession"
category:
tags:
---
##list command
```
Do a long listing and include the size of each file in human-friendly units like megabytes or kilobytes
ls -lh
Do a long listing and include the author of each file
ls -l --author
Sort the directory list by file size
ls -S
Sort the files in reverse order
ls -r
List one file per line
ls -1
ls -L, --dereference
              when showing file information for a symbolic link, show informa-
              tion for the file the link references rather than for  the  link
              itself
```
The normal command for removing a directory is rmdir, which you can remember as "remove directory". You can only remove a directory that is empty with rmdir.

##umask command
hen you create new files, you generally want to have the default set for yourself at the maximum: 7 (read, write, and execute) for directories and 6 (read and write) for files. You probably want your group to be able to read files you create, but not overwrite them unless you specifically want them to, so you would set group permission to 5 (dir) or 4 (file). If you want all users to be able to read your file, you would set that permission to 5 (dir) or 4 (file) as well. So, your desired default permission settings would be 755 or 644.
Now, when you subtract the number 0022 from the default values for directories and files, as shown, you are taking away the permissions you don't want people to have!
```
Directories   Owner Group All
Default directory permissions 0 7 7 7
umask value                         0 0 2 2
numeric subtraction result            7 5 5
permission result                rwx  r-x r-x
Files   Owner Group All
Default directory permissions 0 6 6 6
umask value                         0 0 2 2
numeric subtraction result            6 4 4
permission result                   rw- r-- r--
```
So, setting the umask to 0022 means that when you create a new directory, the default permissions for it will be 755. When you create a new file, the default permissions will be 644. That's a lot more convenient than setting them manually every time , don't you think?


```
ninja@ultimatepower:/tmp$ ls -l
total 0
-rwxr-xr-x 1 ninja ninjas    0 Apr 26 12:07 thestars.txt
```
Note: 0 at here means ninjas only contain one single user, ninja.
```
Acting as sudo (or root), create a new group using the groupadd command, as shown.
ninja@ultimatepower:/tmp$ sudo groupadd piratesandninjas
Now, add pirate to the new group piratesandninjas using the usermod -G command (usermod stands for User Modify, -G for the group option. You can check the man page for that command for lots of details!).
ninja@ultimatepower:/tmp$ sudo usermod -G piratesandninjas pirate

The syntax is chown user:group filename, so type chown yourname:piratesandninjas thestars.txt and press Enter.
ninja@ultimatepower:/tmp$ chown ninja:piratesandninjas thestars.txt
To see what changed, type ls -l and press Enter.
ninja@ultimatepower:/tmp$ ls -l
total 0
-rwxr-xr-x 1 ninja piratesandninjas    0 Apr 26 12:07 thestars.txt
```

In the example, the spaces for thestars.txt are set as follows:
First space Owner Group Other
-                    rwx  r-x         r-x
The first (leftmost) space indicates whether or not a given filename is a directory, a special sort of file (we haven't talked about these yet), or just a plain regular file. If the first space contains a "d", the file is a directory. In our example, there is no "d" because thestars.txt is just a plain old file.
Note: "l" is symbolic link, d is a directory, - is just plain file.
```
Number  Read (r)  Write (w) Execute (x)
0 - - -
1 - - x
2 - w -
3 - w x
4 r - -
5 r - x
6 r w -
7 r w x
```


```
Use cd to change your working directory to coffee.
ninja@ultimatepower:/tmp$ cd coffee/

ninja@ultimatepower:/tmp/coffee$ ls
ls: .: Permission denied
Aha! Permission was denied because you only have execute permission for the directory! You can go inside it, but can't see what's there.
```
This illustrates an important point: Even though you may not be allowed to write to a directory, you may still have write permissions for files inside the directory, depending on how those files were created. Each file has its own permissions that do not automatically change if you move the file into a directory with different permissions.
```
ninja@ultimatepower:/tmp$ cd coffee/

ninja@ultimatepower:/tmp/coffee$ touch this
touch: cannot touch `this': Permission denied
```


##Additional Examples and Exercises
###Task 1
What are the minimum permissions for the coffee directory that you'd need in order to touch the this file? Of course, 777 for coffee works, but what are the minimum permissions for you to be able to touch this?
A: 200

###Task 2
Make a new file using touch named creamer inside the coffee directory. Edit the creamer file so that it has the words "and sugar" in it.
Make a new directory on the same level as coffee named lunchbox.
Inside the lunchbox directory, create files named juiceBox, brownies, and pbjSandwich. You can either edit all of the files so that they contain the word "and sugar" or create the files by making copies of the creamer file (which already contains "and sugar").
Problem
Lucy is a member of your group (You don't need to create Lucy. Just assume she's a member of your group). I (yes, I am the author of this lab, but I could be anyone!) am not you and I am not a member of your group.
Set the minimum permissions needed to:
Keep the lunchbox closed to me.
Allow Lucy to look in the lunchbox, do whatever she wants with the juiceBox and pbjSandwich (including removing the "sugar" inside them). Do not give Lucy permission to do anything to the brownies except see the file. You don't want Lucy to be able to see what they say and you especially do not want her to edit the brownies (Mmmmm... brownies...)!
Do not allow anyone to look at your coffee directory or to see what is in it. It is fine if people know you have a coffee, but it is just downright rude to stick their nose in it and see how much creamer and "sugar" you have in the coffee. Prevent that.
```
chmod 750 coffee
cd coffee
chmod 750 creamer
cd ..
chmod 770 lunchBox
cd lunchBox
chmod 770 juiceBox
chmod 770 pbjSandwich
touch brownies
chmod 740 brownies
```
###Task 3
You have a rather... um, retro pair of very baggy pants (file) in your closet (directory). These have considerable sentimental value to you, but you don't like people to see them because they are so '80s!
Assume that anyone who shares your house (your group) knows about your baggy pants. That is fine. They probably know much worse. You don't mind if they see (read) them either. But you seriously don't want them to wear (execute) your pants nor put anything in the pockets (write). (In other words, the pants file should be read-only for your group.)
The last thing you want is for anyone who does not know already to discover your baggy pants. Ensure that no one outside of your house can see in your closet. (In other words, the closet directory should not be accessible nor should anything in it be visible to anyone outside of your group.)
```
chmod 750 closet
chmod 744 baggy_pants
```

TAKE-AWAY: directory x is to enter the directory but you cant do anything in it except you have permit to write/read. 


http://code.google.com/edu/tools101/linux/ownership_permissions.html
