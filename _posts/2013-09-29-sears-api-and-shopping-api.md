---
layout: post
title: "sears API and shopping API"
category: Java
tags: [Java, BE, APIs]
---
Sears API
---------
very good, and easy to use. The category is clearly defined, so call the API should be easy.     
[sears API](http://developer.sears.com/apis)    

Jersery
-------
Jersery is Java's RESTful package. Use Maven to include it as dependency. 
Client is enough for calling API.
    <dependency>
      <groupId>org.glassfish.jersey.core</groupId>
      <artifactId>jersey-client</artifactId>
      <version>2.3</version>
    </dependency>

Real Java code of Jersery:
    Client client = ClientBuilder.newClient(new ClientConfig());
    WebTarget WebTarget = client.target("http://api.developer.sears.com/v2.1");
    WebTarget resourceWebTarget = WebTarget.path("products");
    String search_path_with_keyword = String.format("search/Sears/json/keyword/%s", keywords);
    System.out.println(search_path_with_keyword);
    WebTarget search_product_target = resourceWebTarget.path(search_path_with_keyword);

    WebTarget search_product_with_params;
    if (pageNumber != -1) {
      int startIndex = (pageNumber)*25+1;
      int endIndex = startIndex+24;
      search_product_with_params = search_product_target.queryParam("apikey", apikey)
      .queryParam("startIndex=", startIndex).queryParam("endIndex=", endIndex);
      System.out.println(String.format("%s %s", startIndex, endIndex));
    }
    else search_product_with_params = search_product_target.queryParam("apikey", apikey);
    Invocation.Builder invocationBuilder =
          search_product_with_params.request(MediaType.APPLICATION_JSON);
    Response response = invocationBuilder.get();
    String res_string = response.readEntity(String.class);

Gson Parser
-----------
very interesting. Every iteration treats the result as JsonObject. 
check [Gson](https://code.google.com/p/google-gson/) for more details.
Shopping API
------------
Ebay's shopping.com API. not very convenient to use, and many information I need is not there (like shipping information: they only provide estimate, which is different to the website)
Use jsoup to screen scrapping would be a better choice.
[Shopping.com API](http://developer.ebaycommercenetwork.com/docs)
