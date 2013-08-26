---
layout: post
title: "Binary search algorithm optimization"
category:
tags:
---
http://en.wikipedia.org/wiki/Binary_search

Deferred detection of equality
The above iterative and recursive versions take three paths based on the key comparison: one path for less than, one path for greater than, and one path for equality. (There are two conditional branches.) The path for equality is taken only when the record is finally matched, so it is rarely taken. That branch path can be moved outside the search loop in the deferred test for equality version of the algorithm. The following algorithm uses only one conditional branch per iteration.[4]
```
// inclusive indices
//   0 <= imin when using truncate toward zero divide
//     imid = (imin+imax)/2;
//   imin unrestricted when using truncate toward minus infinity divide
//     imid = (imin+imax)>>1; or
//     imid = (int)floor((imin+imax)/2.0);
int binary_search(int A[], int key, int imin, int imax)
{
  // continually narrow search until just one element remains
  while (imin < imax)
    {
      int imid = midpoint(imin, imax);
 
      // code must guarantee the interval is reduced at each iteration
      assert(imid < imax);
      // note: 0 <= imin < imax implies imid will always be less than imax
 
      // reduce the search
      if (A[imid] < key)
        imin = imid + 1;
      else
        imax = imid;
    }
  // At exit of while:
  //   if A[] is empty, then imax < imin
  //   otherwise imax == imin
 
  // deferred test for equality
  if ((imax == imin) && (A[imin] == key))
    return imin;
  else
    return KEY_NOT_FOUND;
}
```
