---
layout: post
title: "python 2.7.4 MAXREPEAT issue"
category: python
tags: [python, bug]
---
[good post](http://isotope11.com/blog/fix-your-python-2-dot-7-4-maxrepeat-importerror-issues)
###Solution
reinstall brew python to python 2.7.5
    ### Makes you owner of /usr/local 
    $ sudo chown -R `whoami` /usr/local
    
    ### Force uninstalls failed python
    $ brew uninstall -f python
    
    ### Clear the brew cache
    $ rm -rf `brew --cache`
    
    ### Cleanup - cleans up old homebrew files
    $ brew cleanup
    
    ### Prune - removes dead symlinks in homebrew
    $ brew prune
    
    ### Doctor - runs homebrew checks for common error causing issues
    $ brew doctor
    
    ########
    ### Google and follow anything steps to fix brew doctor might come back with
    ########
    
    ### Reinstall python
    $ brew install python
                                                                                                                                                                                                                                                                                                                                
