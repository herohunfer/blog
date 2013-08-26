---
layout: post
title: "Crack Crack"
category:
tags:
---
Bit Manipulation
Xor (^):0 ^ 0 = 0
1 ^ 0 = 1
0 ^ 1 = 1
1 ^ 1 = 0

5.3
The problem is very hard. Need work step by step.
Notice: the solution wont work well if the number is "special", like 11, 111, 1111, which has all 1's at the end. That's why the author chooses to return -1.
## next integer
```
example: 01100
c0 = 2
c1 = 2
1> flip all c0 to 1 --> 01111
2> add 1 to set p position --> 10000
3> add (c1-1)'s 1 at the back --> 10001
```
##previous integer
```
example: 10011
c0 = 2
c1 = 2
1> flip all c1 to 0 --> 10000
2> decrease by 1 --> 1111
3> modify to set (c0-1)'s 0 at the back. --> 1110 (subtract (c0-1)'s 1')

```
