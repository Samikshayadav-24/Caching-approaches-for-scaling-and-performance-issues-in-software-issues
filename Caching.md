## DIFFERENT TYPES OF SCALABILITY :

#### Performance scalability :
 - Scaling on a system by simply by adding more memory, faster CPU, faster disk, etc (very limited scalability).
 - Scaling by adding multiple CPUs or cores (requires multi-threaded application).
 - Scaling by adding more machines in a network possibly on a load balancer (this is infinite scalability).

#### Functional scalability :
   This kind of scalability allows you to add more capabilities easily.
 - Functional scaling due to information hiding (requires object oriented design).
 - Scaling through meta programming, (requires highly normalized schema and/or meta code that can be configured in different ways).

#### Deployment scalability :
   If you want to add more machines in a network possibly on a load balance, deployment scalability creates a well architected deployment design.

#### Programming scalability :
   This allows large numbers of programmers to work together on a single application. This requires good software engineering practices and good engineering management.


## 1. What is caching ?

Caching is a mechanism to enhance the performance of a system. It is a temporary memory that lies between the application and the persistent database. Cache memory stores recently used data items in order to reduce the number of database hits as much as possible.

Caching is a technique to speed up data lookups (data reading). Instead of reading the data directly from its source, which could be a database or another remote system, the data is read directly from a cache on the computer that needs the data. Here is an illustration of the caching principle:

![caching](https://user-images.githubusercontent.com/66433177/125092881-661e4f00-e0ef-11eb-8c12-656fd4876adb.png)

Caching could be used by different development frameworks, We will be using Spring-Boot to demonstrate caching.  

**_Spring Boot_** helps developers create applications that just run. Specifically, it lets you create standalone applications that run on their own, without relying on an external web server, by embedding a web server such as Tomcat. 

We will manage application **_cache_** from Spring framework caching support. 
Spring has features on caching and the abstraction on the **_spring cache API_** which is very much simple to use.



#### 1.1. Why do we need caching ?

Data access from memory is always faster in comparison to fetching from storage like database, file system or other service calls.

#### 1.2. What data should be cached ?

It varies in different scenarios and requirements on how much time we can tolerate stale data.
So caching candidates will vary on each project, still those are few examples of caching.

- List of products available in an eCommerce store.
- Any Master data which is not frequently changed.
- Any frequently used database read query, where the result does not change in each call at least for a specific period.

## 2. TYPES OF CACHING

#### 2.1. In-memory caching
   - In-memory caching extensively  increases the performance of the application.

   - Memcached and Redis are examples of in-memory caching. It stores key-value between application and database.

   - Redis is an in-memory, distributed, and advanced caching tool that allows backup and restore facility. We can manage cache in distributed clusters, also.

   - RAM is more limited than disk, so cache invalidation algorithms such as least recently used (LRU) can help invalidate ‘cold’ entries and keep ‘hot’ data in RAM.

#### 2.2. Database caching
Database caching is a mechanism that generates web pages on-demand (dynamically) by fetching the data from the database. It is used in a multi-tier environment that involves clients, web-application server, and database. It improves scalability and performance by distributing a query workload. The most popular database caching is the first level cache of Hibernate.

#### 2.3. Web server caching
Web server caching is a mechanism that stores data for reuse. For example, a copy of a web page served by a web server. It is cached for the first time when a user visits the page. If the user requests the same next time, the cache serves a copy of the page. It avoids the server from getting overloaded. Web server caching enhances the page delivery speed and reduces the work to be done by the backend server.

#### 2.4. CDN caching
The CDN stands for Content Delivery Network. It is a component used in modern web applications. It improves the delivery of the content by replicating commonly requested files (such as HTML Pages, stylesheet, JavaScript, images, videos, etc.) across a globally distributed set of caching servers.
It is the reason CDN became more popular. The CDN reduces the load on an application origin and improves the user experience. It delivers a local copy of the content from a nearby cache edge (a cache server that is closer to the end-user), or a Point of Presence (PoP).

## Resources
- [Wikipedia](https://en.wikipedia.org/wiki/Cache_(computing))
- [GeeksforGeeks](https://www.geeksforgeeks.org/cache-memory/)
- [Amazon.com](https://aws.amazon.com/caching/#:~:text=In%20computing%2C%20a%20cache%20is,the%20data's%20primary%20storage%20location.)
- [Cloudfare.com](https://www.cloudflare.com/en-in/learning/cdn/what-is-caching/)
- [auth0.com](https://auth0.com/blog/what-is-caching-and-how-it-works/#Types-of-Caching)
- [howtodoinjava.com](https://howtodoinjava.com/spring-boot2/spring-boot-cache-example/)
- [tutorials.jenkov.com](http://tutorials.jenkov.com/software-architecture/caching-techniques.html)
- [Reference paper](https://arxiv.org/pdf/1805.11721.pdf)
