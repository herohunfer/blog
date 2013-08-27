---
layout: post
title: "mySQL full text"
category:
tags:
---
Consider our table above. What if we need to search for keywords in both the title and the body? An easy solution is to add a fulltext index:
    ALTER TABLE mysqltest.articles ADD FULLTEXT alltext (title, body);
We can now find all articles that feature the words “database” and/or “article” using:
    SELECT * FROM mysqltest.articles
    WHERE MATCH(title, body) AGAINST ('database article');
We can even order articles by the most relevant first to create a simple search engine:
    SELECT *, MATCH(title, body) AGAINST ('database article') AS rel
    FROM mysqltest.articles
    ORDER BY rel DESC;
