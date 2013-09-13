---
layout: post
title: "copy constructor of ArrayList"
category: java
tags: [java, trick]
---
copy constructor
----------------
    ArrayList<ArrayList<Integer>> result = new ArrayList<ArrayList<Integer>>(previous);    
this will not work because copy constructor can not go two level deep. Correct way is:
    ArrayList<ArrayList<Integer>> result = new ArrayList<ArrayList<Integer>>();
    for (ArrayList<Integer> a : previous) {
      result.add(new ArrayList<Integer>(a));
    }
