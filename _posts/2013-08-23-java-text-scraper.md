---
layout: post
title: "Java Text Scraper"
category: java
tags: [java, jsoup]
---
Run java program with class path:
javac -cp ".:jsoup-1.7.2.jar" HTMLQuery2.java

Create Jar file with manifest
jar -cvfm Assignment.jar manifest.txt HTMLQuery.class ResultObject.class
http://www.mkyong.com/java/how-to-make-an-executable-jar-file/


Manifest File

Main-Class: HTMLQuery
Class-Path: jsoup-1.7.2.jar


include jar dependency into jar file
http://docs.oracle.com/javase/tutorial/deployment/jar/downman.html
