---
layout: post
title: "traverse hashmap"
category: java
tags: [java]
---
##Traverse HashMap
    for (String key: hash.keySet()) {
      ...
    }
    
    for (Map.Entry<String, Object> entry: map.entrySet()) {
      String key = entry.getKey();
      Object value = entry.getValue();
      // ...
    }
    
##Traverse HashMap only keys or values
    Map<String, Object> map = ...;
    
    for (String key: map.keySet()) {
      // ...
    }
or only values:
    for (Object value : map.values()) {
      // ...
    }
    
##Using iterators
    Map<Integer, Integer> map = new HashMap<Integer, Integer>();
    Iterator<Map.Entry<Integer, Integer>> entries = map.entrySet().iterator();
    while (entries.hasNext()) {
      Map.Entry<Integer, Integer> entry = entries.next();
      System.out.println("Key = " + entry.getKey() + ", Value = " + entry.getValue());
    }
##HashTable vs HashMap
> There are several differences between HashMap and Hashtable in Java:
> 
> Hashtable is synchronized, whereas HashMap is not. This makes HashMap better for non-threaded applications, as unsynchronized Objects typically perform better than synchronized ones.
> Hashtable does not allow null keys or values. HashMap allows one null key and any number of null values.
> One of HashMap's subclasses is LinkedHashMap, so in the event that you'd want predictable iteration order (which is insertion order by default), you could easily swap out the HashMap for a LinkedHashMap. This wouldn't be as easy if you were using Hashtable.
> Since synchronization is not an issue for you, I'd recommend HashMap. If synchronization becomes an issue, you may also look at ConcurrentHashMap.
