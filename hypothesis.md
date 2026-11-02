HYPOTHESIS

Suspect            : I think Keycloak might slow down when too many users try to log in at the same time.

Predicted signal   : what else should change if I am right? The p95 response time should increase, and the number of requests per second may not increase as much as the number of users.

Intervention       : the one thing I will change is increasing the number of simulated users from 10 to 20 and keep the other test settings the same.

Falsifier          : what result would prove me wrong? If the response time stays almost the same and the number of requests per second nearly doubles, my hypothesis is probably wrong.

I tested Keyclock with 20 users instead of 10 while keeping the other test settings the same. The p95 response ttime increased from 189.28ms to 230.27ms. The average response time
increased from 170.60ms to 207.98 ms. No errors were observed.
The results support my prediction that response times would increase with more users. However, the system also handled more requests, so we cannot conclude that Keyclock has reached the maximum capacity (bottleneck).