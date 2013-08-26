---
layout: post
title: "Google Grep Lession"
category:
tags:
---
```
cat
sort
wc
wc -L
wc -wcl
```
### reverse grep
```
ninja@ultimatepower:~$ grep -v berries fruits.txt
kiwi
orange
apple
plum
banana
```

###add>
```
ninja@ultimatepower:~$ grep -v berries fruits.txt > not_berries.txt
```
###append >>
```
ninja@ultimatepower:~$ grep -v berries purplestuff.txt >> not_berries.txt
```
### pipe |
```
ninja@ultimatepower:~$ grep -v berries purplestuff.txt | grep ^b
balloons
bass guitar
```
###tee
the tee command writes the input it receives to a file you specify and also sends the text to standard output (usually your monitor). The tee command is really helpful when you want to use > or > to save the results of a grep command, but you also need to see those results immediately.
```
ninja@ultimatepower:~$ cat not_berries.txt | tee still_not_berries.txt
kiwi
orange
```
###Greppin' multiple files at once
```
ninja@ultimatepower:~$ cat fruits.txt purplestuff.txt | grep berries
glitterberries
purpleberries
berries
purpleberries 
```

Question: How many unique types of berries are there within fruits.txt and purplestuff.txt?
```
ninja@ultimatepower:~$ cat fruits.txt purplestuff.txt | grep berries | sort -u | wc -l
3 
```
Notice the use of word count

##Additional Examples and Exercises
###Lookin' for files in the GNU world
Use a pipe to combine the ls and grep commands into a single command that lists all the files in /usr/bin that have the word "make" anywhere in the filename.
A: ls | grep make

###Advanced work: How many p's?
Still working with fruits.txt and purplestuff.txt, see if you can discover how to use the tools you have learned about to:
- Determine how many unique words in the files start with the letter "p",

A: cat fruits.txt purplestuff.txt | grep ^p | sort -u

- List the words you find, sorted in reverse alphabetical order

A: cat fruits.txt purplestuff.txt | grep ^p | sort -ur

- Return the filename where each string (including duplicates) was found, along with the returned string.

A: cat fruits.txt purplestuff.txt | grep ^p -H

