---
layout: post
title: "regular expression"
category:
tags:
---
[abc]   
[^abc]    
[a-zA-Z]    
[a-d[m-p]]    
[a-z&&[def]] = [def]    
[a-z&&[^bc]]    
[a-z&&[^m-p]]   

.     Any Character   
\d    [0-9]   
\D    [^0-9]    
\s    [\t\n\x0B\f\r]  white space character   
\S    [^\s]   
\w    [a-zA-Z_0-9] word character   
\W    [^\w]   

private final String REGEX = "\\d"; // a single digit   
    
X?    once or not at all    
X*    zero or more times    
X+    one or more times   
X{n}  exactly n times   
X{n,} at least n times    
X{n,m} at least n but no more than m times    

(dog){3} == (dogdogdog)   

Enter your regex: (\d\d)\1    
Enter input string to search: 1212    

means match any 2 digits follow by exact same two digits    

Boundary Matchers
-----------------
^       The beginning of a line   
$       The end of a line   
\b      a word boundary   
\B      a non-word boundary   
\A      the beginning of the input    
\G      the end of the previous match   
\Z      the end of the input but the final terminator if any    
\z      the end of the input    

    Enter your regex: \s*dog$   
    Enter input string to search:             dog   
    I found the text "            dog" starting at index 0 and ending at index 15.    

Embedded Flag Expression
------------------------
Enter your regex: (?i)foo   
Enter input string to search: FOOfooFoOfoO    

?i      Pattern.CASE_INSENSITIVE


