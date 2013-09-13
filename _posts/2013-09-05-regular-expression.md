---
layout: post
title: "regular expression"
category:
tags:
---
java requires double slash to escape character. \\s \\d others may only need one.   
###java regex
    import java.util.regex.Matcher;
    import java.util.regex.Pattern;
    Pattern pattern = Pattern.compile("\\d");
    Matcher matcher = pattern.matcher(s);
###understand ? lazy operator
.*? will match only the first one. regEX are greedy.
(?: non-capture sequence)  
###address match
5995 Mowry Ave Newark, CA 
1602 S. El Camino Real, San Mateo CA
wrong with: 9966 Bombay Garden 3701 El Camino Real Santa Clara, CA 

(\\d){3}\\d?\\s[\\w\\d\\.\\,\\s]+(?=AL|AK|AS|AZ|AR|CA|CO|CT|DE|DC|FM|FL|GA|GU|HI|ID|IL|IN|IA|KS|KY|LA|ME|MH|MD|MA|MI|MN|MS|MO|MT|NE|NV|NH|NJ|NM|NY|NC|ND|MP|OH|OK|OR|PW|PA|PR|RI|SC|SD|TN|TX|UT|VT|VI|VA|WA|WV|WI|WY)[A-Z]{2}[\\,\\s]+(?:-\\d{5}\\d{4})?)

### phone number
\\(?(\\d){3}[\\])\\.\\-]?\\s?(\\d){3}[\\.\\-](\\d){4}
(123)456-7890
(123) 456.7890
123.456.7890

###cheat sheet
[CheatSheet](http://regexlib.com/CheatSheet.aspx)
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


