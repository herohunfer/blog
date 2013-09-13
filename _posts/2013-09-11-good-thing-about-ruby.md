---
layout: post
title: "good thing about ruby"
category: ruby
tags: [ruby]
---
1. array can be variant length
    my_array = [[1,2,3],[2,3],[3]]

2. hash is easy to understand
    hash = Hash.new
    hash = {"aunt" => "ma",
            "uncle => "fu"}

3. no indentation requirement (good or bad?)

4. sort function
    frequencies = frequencies.sort_by{|a, b| b}

5. lambda function
    1.times do
      puts "I'm a code block!"
    end
    
    1.times { put "As am I!" }

6. easy comparator
    //sort fruits in descending order
    fruits.sort!{|first, second| second<=>first}
    
