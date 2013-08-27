---
layout: post
title: "crack chapter 10 scalability and memory limit"
category:
tags:
---
##Handle Millions of User
1. avoid using arrays, use arraylist instead (dynamic data structure)
2. multiple machines
        public class server {
          HashMap<Integer, Machine> machines = new HashMap<Integer, Machine>();
          HashMap<Integer, Integer> personToMachineMap = new HashMap<Integer, Integer>();

          public Machine getMachineWithId(int machineID) {
            return machines.get(machineID)
          }
          
          public int getMachineIDForUser(int personID) {
            Integer machineID = personToMachineMap.get(personID);
            return machineID == null ? -1 : machineID;
          }
          
          public Person getPersonWithID(int personID) {
            Integer machineID = personToMachineMap.get(personID);
            if (machineID == null) return null;
        
          Machine machine = getMachineWithId(machineID);
            if (machine == null) return null;

            return machine.getPersonWithID(personID);
          }
        }
        public class Person {
          private ArrayList<Integer> friendIDs;
          private int personID;
          
          public Person(int id) { this.personID = id; }
          
          public int getID() { return personID; }
          public void addFriend(int id) {friends.add(id);}
        }
         
        public class Machine {
          public HashMap<Integer, Person> persons = new HashMap<Integer, Person>();
          public int machineID;

          public Person getPersonWithID(int personID) {
            return persons.get(personID);
          }
        }

##Bit Vector
  // create a Bit Vector to mark the existing number e.g. bitfield[n] = 1
  byte[] bitfield = new byte [0xFFFFFFF/8];
  // mark existed
  bitfiled[n/8] |= 1 << (n%8);
  // check if existed; if not then output
  if ((bitfield[i] & (1 << j)) == 0) {
    System.out.println(i*8 + j);
    return;
  }
