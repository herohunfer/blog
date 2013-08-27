---
layout: post
title: "mySQL engines"
category: mysql
tags: mysql
---
[Pros and Cons](http://www.sitepoint.com/mysql-myisam-table-pros-con/)
Use InnoDB to enable features like NOT NULL
default table engine is MyISAM
MyISAM                                Innodb
No ACID non-transactional           ACID compliant fully transactional
                                    with ROLLBACK and COMMIT
                                    support Foreign keys

MySQL 5.0 Default Engine            Rackspace Cloud Default Engine

Require Full repair/rebuild of      Auto Recovery from crash via replays of logs
indexs/tables

Changed DB pages written to         Dirty pages converted from random to 
disk instantly                      sequential before comit and flush to disk

No ordering in storage of data      Row data stored in pages in PK order

Table level locking                 Row level locking

##How to change
ALTER TABLE <table-name> ENGINE=INNODB;
