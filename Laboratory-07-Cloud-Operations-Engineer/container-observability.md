# Container Observability

## Application Logs

404 error line from the container's access log:
Application logs are vital for troubleshooting because they record exactly what was requested, when, and what the server returned, letting an engineer pinpoint the precise request that failed instead of guessing. Without logs, diagnosing an intermittent or user-reported issue would require reproducing it blind, with no record of what actually happened on the server.

## Real-Time Container Metrics

At the time of the screenshot, the `client-website` container was consuming:

- **Memory Usage:** 2.73MiB / 1.859GiB
- **CPU Usage:** 0.00%
