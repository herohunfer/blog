---
layout: post
title: "Five Essential Phone Screen Questions"
category:
tags:
---
The Five Essential Phone-Screen Questions Learning
https://sites.google.com/site/steveyegge2/five-essential-phone-screen-questions
#Coding
System.out.print ( String.format ( "%4d", j * i )); to regular the output

Example 7:  Format an RGB value (three 1-byte numbers) as a 6-digit hexadecimal string.

Java:

    public String formatRGB ( int r, int g, int b ) {
        return (toHex(r) + toHex(g) + toHex(b)).toUpperCase();
    }

    public String toHex ( int c ) {
        String s = Integer.toHexString ( c );
        return ( s.length() == 1 ) ? "0" + s : s;
    }
Or in Java 1.5:

    public String formatRGB ( int r, int g, int b ) {
        return String.format ( "%02X%02X%02X", r, g, b );
    }

# OOP
* virtual method, pure virtual method
* multiple inheritance (and give an example)
* delegation/forwarding
* method overriding
* method overloading (and difference from overriding)
* method signatures (what's included in one)
in the Java programming language, a method signature is the method name and the number and type of its parameters. Return types and thrown exceptions are not considered to be a part of the method signature.


a car with a bumper sticker is a subclass of car is a car class with a bumper sticker attribute, other than a new car inheritance.

1. Model the Animal kingdom as a class system, for use in a Virtual Zoo program.

Possible sub-issues: do they know the animal kingdom at all? (I.e. common sense.) What properties and methods do they immediately think are the most important? Do they use abstract classes and/or interfaces to represent shared stuff? How do they handle the multiple-inheritance problem posed by, say, a tomato (fruit or veggie?), a sponge (animal or plant?), or a mule (donkey or horse?)

2. Create a class design to represent a filesystem.

Do they even know what a filesystem is, and what services it provides? Likely classes: Filesystem, Directory, File, Permission. What's their relationship? How do you differentiate between text and binary files, or do you need to? What about executable files? How do they model a Directory containing many files? Do they use a data structure for it? Which one, and what performance tradeoffs does it have?

3. Design an OO representation to model HTML.

How do they represent tags and content? What about containment relationships? Bonus points if they know that this has already been done a bunch of times, e.g. with DOM. But they still have to describe it.


My weakest point: Area Number Three: Scripting and Regular Expressions
grep. find. try to find the last command we use for Computer Structure lab.


byte, short, int, long, float, double, char, boolean
* Write a function to count all the bits in an int value; e.g. the function with the signature int countBits(int x)
* Describe a function that takes an int value, and returns true if the bit pattern of that int value is the same if you reverse it (i.e. it's a palindrome); i.e. boolean isPalindrome(int x)
