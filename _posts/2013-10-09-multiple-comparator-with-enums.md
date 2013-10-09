---
layout: post
title: "multiple comparator with enums"
category: java
tags: [java, trick]
---
[a brilliant post](http://stackoverflow.com/questions/1421322/how-do-i-sort-a-list-with-multiple-sort-parameters)
Question:    
I have a class named Person with multiple properties, for example:    

    public class Person {
        private int id;
        private String name, address;
        // Many more properties.
    }
A lot of Person-objects are stored in an ArrayList<Person>. I want to sort this list by multiple sort parameters, and different from time to time. For instance I might one time want to sort by name ascending and then address descending, and another time just by id descending.    

And I don't want to create my own sort methods (i.e., I want to use Collections.sort(personList, someComparator). What is the most elegant solution that achieves this?)

Answer:    
    enum PersonComparator implements Comparator<Person> {
        ID_SORT {
            public int compare(Person o1, Person o2) {
                return Integer.valueOf(o1.getId()).compareTo(o2.getId());
            }},
        NAME_SORT {
            public int compare(Person o1, Person o2) {
                return o1.getFullName().compareTo(o2.getFullName());
            }};
    
        public static Comparator<Person> decending(final Comparator<Person> other) {
            return new Comparator<Person>() {
                public int compare(Person o1, Person o2) {
                    return -1 * other.compare(o1, o2);
                }
            };
        }
    
        public static Comparator<Person> getComparator(final PersonComparator... multipleOptions) {
            return new Comparator<Person>() {
                public int compare(Person o1, Person o2) {
                    for (PersonComparator option : multipleOptions) {
                        int result = option.compare(o1, o2);
                        if (result != 0) {
                            return result;
                        }
                    }
                    return 0;
                }
            };
        }
An example of usage(with a static import).    
    public static void main(String[] args) {
        List<Person> list = null;
        Collections.sort(list, decending(getComparator(NAME_SORT, ID_SORT)));
    }
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    }
