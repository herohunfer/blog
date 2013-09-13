---
layout: post
title: "Edge javascript learning"
category: javascript
tags: [javascript, phantomJS]
---
###output to a local file
    var fs = require('fs');
    
    page.open("http://www.google.com", function(status)) {
      fs.write('input.html', page.content, 'w');
    }
###phantomJS
phantomJS is a good tool to screen capture. It will allow javascript to be fully rendered and then capture the HTML page, which means what you get is exactly what you see.
    var system = require('system');
    var page = require('webpage').create();
    if (system.args.length == 1) {
      console.log('Usage: input.js <some URL>');
      phantom.exit(1);
    } else {
      page.open(system.args[1], function(status) {
        if (status != 'success')
          console.log('FAIL to load the address');
        else {
          console.log(system.args[1]);
          console.log(page.content);
          render('input.png');
        }
        phantom.exit();
      });
    } 
render only supports PNG, GIF, JPEG and PDF format.

check [phantom API](https://github.com/ariya/phantomjs/wiki/API-Reference-WebPage)
