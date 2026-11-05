CLAIM CARD

Operation        : POST /realms/perf/protocol/openid-connect/token

Workload         : 10 users, think time between 0.1 and 0.3 seconds, duration 35 seconds (5 seconds warmup), cache state warmed by previous logins.

Statistic        : p50, p95, p99 / mean / error rate — Percentile estimator: : linear interpolation at (n-1)\*p.

n observed       : 784 requests (first run), 775 requests (2nd run), 792 requests (3rd run). Total: 2351 requests.

Threshold        : Error rate stays below 1% over each 30-second measurement window.

Decision rule    : Ship if the error rate stays below 1% in all three baseline runs. Hold if the error rate reaches or exceeds 1% in any run.

Limitation       : This claim only covers the tested workload and environment under normal operation. Although I tested Keycloak restarts and       PostgreSQL failures separately, these experiments do not guarantee that the system will behave the same way under different workloads, cache conditions or failure scenarios.

