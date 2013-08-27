---
layout: post
title: "Heap PriorityQueue"
category:
tags:
---
[java doc](http://docs.oracle.com/javase/6/docs/api/java/util/PriorityQueue.html)
[Wiki Heap](http://en.wikipedia.org/wiki/Heap_(data_structure))

##Max PriorityQueue (Max Heap)
    class MaxComparator implements Comparator<Integer> {
      public int compare(Integer a, Integer b) {
        return b-a;
      }
    }
    public class PriorityQueueTest {
      public static void main(String[] args) {
        PriorityQueue<Integer> pr = new PriorityQueue<Integer>();
        pr.add(1);
        pr.add(2);
        pr.add(3);
        while (!pr.isEmpty()) {
          System.out.println(pr.poll());
        }
        PriorityQueue<Integer> pr2 = new PriorityQueue<Integer>(10, new MaxComparator());
        pr2.add(1);
        pr2.add(2);
        pr2.add(3);
        while (!pr2.isEmpty()) {
          System.out.println(pr2.poll());
        }
        
      }
    }
                                                                                                                                                                                                                                                                                                                            
