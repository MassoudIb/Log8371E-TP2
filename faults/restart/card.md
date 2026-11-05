FAULT CARD : Keycloak Restart


Steady-stage claim: Under normal operation with 10 users, i expect the error rate to stay below 1% and the p95 time to stay close to the baseline (around 200ms) before the fault.

Fault: Restart Keycloak while Locust is running.

Blast radius: Only my local Docker test environment is affected. No real users are involved.

Stop condition: Stop the test if Keycloak doesn't become ready within 60 seconds

Observed: During the test, 341 out of 1539 requests failed (22.16%). Error appeared between 20 and 35 seconds. No errors were observed after 35 seconds.

What this shows: Restarting Keycloak caused temporary login failures. After the restart, the system recovered and requests started working again.

Load generator observation: I noticed that during the restart, the number of requests increased around 130 to 210 in 5 seconds interval. I think this happened because some failed requests finished faster. The load generator may have increased the number of requests during the failure. The behavior of Locust may have influenced the number of errors observed. So we have to be more careful when interpreting results.