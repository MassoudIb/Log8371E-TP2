FAULT CARD : Proxy Latency

Steady-state claim: With 10 users using proxy with no added delay, p95 response time stays below 220ms and I expect the error rate to stay below 1% during normal operation.

Fault: Adding 300ms of delay between the proxy and Keycloak for 20 seconds.

Blast radius: Only the local Docker test environment is affected. The delay will automatically expire after 20 seconds.

Stop condition: Stop the test if errors continue for a long time.

Expected: I expect the response time will be increasing when delay is added, but most login requests should still succeed. 

Observed: Without the delay, 1413 requests succeeded with a p95 of 201.96ms. With the delay experiment, 1198 requests succeeded with a p95 of 477.57ms. No errors were observed in both tests.

What this shows: Adding 300ms of delay made the logins requests slower. However, the system continue to work without errors during the experiment.

