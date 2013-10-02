---
layout: post
title: "java comparable and comparator example"
category: java
tags: [java, tricks]
---
Mkyong did a good job [Java Object Sort Example](http://www.mkyong.com/java/java-object-sorting-example-comparable-and-comparator/)   

1. sort an arraylist using Collections.sort()
2. Comparable will enable Arrays.sort algorithm, and it needs implement compareTo function:
    public class Fruit implements Comparable<Fruit> {
      //...
      public int compareTo(Fruit compareFruit) {
        return this.quantity - compareFruit.quantity;
      }
    }
3. Comparator: additional comparator for arrays.sort function
    public class FruitComparator implements Comparator<Fruit> {
      //...
      public int compare(Fruit f1, Fruit f2) {
        return f1.name.compareTo(f2.name);
      }
    }

