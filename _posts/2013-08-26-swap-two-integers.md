---
layout: post
title: "swap two integers"
category: tricks
tags: [algorithm, tricks]
---
* bit manipulation    
    arr[left]^= arr[right];
    arr[right]^= arr[left];
    arr[left]^= arr[right];
* plus minus    
    arr[left] += arr[right];
    arr[right] = arr[left] - arr[right];
    arr[left] -= arr[right];
