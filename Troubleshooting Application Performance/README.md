Troubleshooting Application Response
=========

Moodle or any other application is taking too much time to respond and throwing some 502 error from time to time.

## There are several reasons behind application is taking too much time to respond and throw 502 Gateway timeout Error. Let's discuss each reason one by one.
-------------------------

1. Inadequate server side caching
2. Lack of a CDN
3. Images and videos aren't optimized

## I'll troubleshoot this issue by performing these tasks. 
-------------------------

1. Traces the route using Tracert that data packets sent to and from my IP address take, and calculates the amount of time taken. An issue that may occur is increased latency.

2. Checking Database : In most database-driven applications, the database is the first place where performance issues arise, especially as the data scales. Sometimes application works fine with just a few records in the database can grind to a halt when data rise. How many sql queries are running on that page and see which are the queries are taking time and fix those.
If MySQL has a large amount of data, i'll go for indexing in the database.

3. If it isn't the database, i'll look at the PHP performance and code. Code improvement is another important thing for performance optimization. Try to improve that code so that sql query don't execute in loop

4. If this problem arise time to time then i'll consider to upgrade PHP version because contributors are working hard to optimize PHP performance in each version and introducing updates for security and better performance.

5. Also i'll check application logs because it can provide us useful information that help us to debug further.

Customers are getting 502 error then in this case i'll try to access website within server through localhost. If it's accessible then might be requests are blocked by firewall, so i will disable firewall temporarily and try to access from outside using DNS, Loadbalancer endpoint. 

I'll check for recent deployments and if it's created a problem due to code issue. 

Sometimes we change DNS value so we should also check for recent DNS Changes.

