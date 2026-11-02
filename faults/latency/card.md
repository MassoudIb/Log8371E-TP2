FAULT CARD : Proxy Latency



Steady-state claim: With 10 users and no added delay, I expect the error rate to stay below 1%.



Fault: Adding 300ms of delay between the proxy and Keycloak for 20 seconds.



Blast radius: Only the local Docker test environment is affected. The delay will automatically expire after 20 seconds.



Stop condition: Stop the test if errors continue for a long time.



Expected: I expect the response time will be increasing when delay is added, but most login requests should still succeed. 



Observed: will complete after experiment.



What this shows: will complete after experiment.

