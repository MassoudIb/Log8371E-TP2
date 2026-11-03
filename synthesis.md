# **Synthesis**



* ##### **Bottleneck hypothesis from 3.5**

At first I thought that Keycloak would become slower if more users tried to login simultaneously. To test this, I compared the results with 10 and 20 users. With 10 users, the p95 response time was between 189 and 198ms. When I increased the number of users to 20, the p95 increased to 230.37ms. This shows that the response time increased when I added more users. However, Keycloak was also able to handle more requests. Therefore, I can't really say that I found a bottleneck. If i repeated the test with 20 users and the p95 stayed around 190-200ms, I would have to reconsider my hypothesis. So that single measurement would change my mind about it.



* ##### **Chaos hypothesis**

***What I expected fault 2 to show, and what it showed instead***: 

Before stopping PostgreSQL, I expected some login requests to fail because Keycloak uses the database. I was really surprised to see that user1 had no errors during the test! All 1414 requests succeeded even though I temporarily stopped PostgreSQL. I tried the experiment with user30 who had never logged in before. This time, all 14 requests failed with HTTP 500 errors. Afterwards, when restarting the database, I tested user30 again and all 27 requests succeeded.

***If they differ, why?***

I believe Keycloak probably kept information about user1 in its cache. This could explain why the requests still worked. On the other hand, for user30, Keycloak may have needed to access the database first in order to get information in its cache. I did not check what was stored in the cache. So i cannot be sure 100% that caching was the reason. 



* ##### **What I cannot conclude:**

I cannot say that Keycloak would perform the same way if users sent requests more frequently, because I always used a think time between 0.1 and 0.3 seconds during my tests.

