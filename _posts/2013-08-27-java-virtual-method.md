---
layout: post
title: "java virtual method"
category: java,trick
tags: [java, trick]
---
[java_polymorphism](http://www.tutorialspoint.com/java/java_polymorphism.htm)
    Salary s = new Salary("Mohd Mohtashim", "Ambehta, UP", 3, 3600.00);
    Employee e = new Salary("John Adams", "Boston, MA", 2, 2400.00);
    System.out.println("Call mailCheck using Salary reference --");
    s.mailCheck();
    System.out.println("\n Call mailCheck using Employee reference--");
    e.mailCheck();
for the Employee e, mailCheck in Employee is used in complie time to validate the statement, while in run time, JVM invokes mailCheck() in salary class.    

This is called virtual invocation. and the methods are referred to virtual methods.
