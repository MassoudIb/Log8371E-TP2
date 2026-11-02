HYPOTHESIS

&#x20; Suspect            : I think Keycloak might slow down when too many users try to log in at the same time.

&#x20; Predicted signal   : what else should change if I am right? The p95 response time should increase, and the number of requests per second may not increase as much as the number of users.

&#x20; Intervention       : the one thing I will change is increasing the number of simulated users from 10 to 20 and keep the other test settings the same.

&#x20; Falsifier          : what result would prove me wrong? If the response time stays almost the same and the number of requests per second nearly doubles, my hypothesis is probably wrong.

