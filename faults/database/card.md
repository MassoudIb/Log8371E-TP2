FAULT CARD : Database Failure



Steady-state claim: With 10 users, the error rate should stay below 1% during normal operation.



Fault: Stop the PostgreSQL database while Locust is running.



Blast radius: Only the local Docker test environment will be affected. The database will be restarted within 20 seconds.



Stop condition: Restore the database within 20 seconds. Stop the test if errors continue or the system does not recover.



Expected: I think some login requests might fail while the database is stopped.



Observed: With user1, all 1414 measured requests succeeded. However with user30, all 14 requests failed with HTTP 500 errors.



What this shows: Keycloak continued working for the previously authenticated user, but the user who had never logged in could not authenticate while the database was stopped. This suggest that caching played a role. But, this does not prove that all authentication requests will work without the PostgreSQL database.

