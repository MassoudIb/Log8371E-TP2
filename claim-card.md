CLAIM CARD

&#x20; Operation        : POST /realms/perf/protocol/openid-connect/token

&#x20; Workload         : 10 users, think time between 0.1 and 0.3 seconds, duration 35 seconds (5 seconds warmup), cache state warmed by previous logins.

&#x20; Statistic        : p50, p95, p99 / mean / error rate — Percentile estimator: : linear interpolation at (n-1)\*p.

&#x20; n observed       : 784 requests (first run), 775 requests (2nd run), 792 requests (3rd run). Total: 2351 requests.

&#x20; Threshold        : Error rate stays below 1% over each 30-second measurement window.

&#x20; Decision rule    : Ship if the error rate stays below 1% in all three baseline runs. Hold if the error rate reaches or exceeds 1% in any run.

&#x20; Limitation       : This claim only covers the tested workload and environment. It does not guarantee reliability with more users, different cache conditions, or during server and database failures.

