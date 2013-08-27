---
layout: post
title: "Crack chapter 14 Java"
category: java, trick
tags: [java, trick, bloomberg]
---
##ArrayList vs Vector    
a vector is very similar to an arrayList, except it is synchronized. Its syntax is almost identical as well.   

-------    

##HashMap
Hashtable is synchronized, whereas HashMap is not. This makes HashMap better for non-threaded applications, as unsynchronized Objects typically perform better than synchronized ones.    

Hashtable does not allow null keys or values. HashMap allows one null key and any number of null values.   

One of HashMap's subclasses is LinkedHashMap, so in the event that you'd want predictable iteration order (which is insertion order by default), you could easily swap out the HashMap for a LinkedHashMap. This wouldn't be as easy if you were using Hashtable.    

Since synchronization is not an issue for you, I'd recommend HashMap. If synchronization becomes an issue, you may also look at ConcurrentHashMap.    

Bottom line: the only reason to use Hashtable is when a legacy API (from ca. 1996)   

--------
#interface
    public interface Animal {
      public void eat();
      public void travel();
    } 
Extending interface
    public interface BigAnimal extends Animal {
      public void run();
    }
Interfaces are not classes, however, and an interface can extend more than one parent interface.   
    public interface Hockey extends Sports, Event

#Reflection
Reflection is commonly used by programs which require the ability to examine or modify the runtime behavior of applications running in the Java virtual machine
A good example : [here](http://docs.oracle.com/javase/tutorial/reflect/member/methodInvocation.html)


#Iterable 
    public class CircularArray<T> implements Iterable<T> {
      public Iterator<T> iterator() {
        return new CircularArrayIterator<T>(this);
      }
    }
    private class CircularArrayIterator<TI> implements Iterator<TI> {
      private int _current = -1;
      private TI[] _items;
      
      public CircularArrayIterator(CircularArray<TI> array) {
        _items = array.items;
      }
    
      @Override
      public boolean hasNext() {
        return current < item.length - 1;
      }
      @Override
      public TI next() {
        _current++;
        TI items = (TI) _items[convert(_current)];
        return item;
      }
      @Override
      public void remove() {
        throw new UnsupportedOperationException("...");
      }
                                                                                                                                                                                                                                                                                                        }
