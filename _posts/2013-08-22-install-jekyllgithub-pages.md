---
layout: post
title: "install jekyll+github pages"
category: jekyll
tags: [jekyll, github]
---
#Install Ruby, Gems, RVM
github-pages need Ruby 1.9.3, so update ruby, gems with RVM.
[a good guide](http://architects.dzone.com/articles/upgrading-ruby-20-mountain)
    rvm get update
    gem update --system
    gem update
    brew update
    brew doctor
    brew install libyaml
    rvm pkg install openssl
    rvm install 1.9.3

make sure run the following command to enable ruby 1.9.3:
    rvm use 1.9.3 --default

# Home Brew
use the fllowing command to make home brew local and available to install locally without root.
    sudo chmod -R g+w /usr/local/
    sudo chmod -R g+w /Library/Caches/Homebrew

# Rakefile
    rake post title="hello"
if not working, make sure rakefile is there.

# Style problem
if no style shown on github pages, add media/ folder into github.com project. This will allow /media/css/ and /media/js/ loaded onto github and support the blog.

# Reference
a great jekyll installation guide (a lot of detail involved) [How I build my blog in one day](http://erjjones.github.io/blog/How-I-built-my-blog-in-one-day/)
[use jekyll to write blogs](http://webfrogs.me/2012/12/20/use-jekyll/)
[a beautiful blog](www.mingxinglai.com)
