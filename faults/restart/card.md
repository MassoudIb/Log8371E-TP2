FAULT CARD : Keycloak Restart



Steady-stage claim: with 10 users, i expect the error rate to stay below 1% and the p95 time toe stay close to the baseline (around 200ms) before the fault.



Fault: Restart Keyclock while Locust is running.


Blast radius: Only my local Docker test environment is affected. No real users are involved.


Stop condition: Stop the test if Keycloak doesn't become ready within 60 seconds


Observed: During the test, 341 out of 1539 requests failed (22.16%). Error appeared between 20 and 35 seconds. No errors were observed after 35 seconds.


What this shows: Restarting Keycloak caused temporary login failures. After the restart, the system recovered and requests started working again.

