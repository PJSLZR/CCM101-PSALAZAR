# Laboratory 7: The Cloud Operations Engineer

## Mission Overview

As part of the Cloud Operations Team (SRE) at CloudNova Technologies, I performed a baseline health check on a production server ahead of a marketing campaign surge. This included checking host CPU, memory, and disk capacity, deploying the client's Nginx web server, generating test traffic (including a simulated 404 error), and capturing both application logs and real-time container resource metrics to verify the infrastructure was ready.

## Objectives

- Utilize native Linux command-line tools to monitor host CPU, Memory, and Disk capacity.
- Deploy a web container and track its real-time performance using Docker metrics.
- Generate web traffic and extract application access logs for analysis.
- Translate raw performance data into a readable technical report using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

## Monitoring Commands Executed

| Command | Purpose | Evidence |
|---|---|---|
| `free -h` | Check the total and available memory (RAM) | memory-check.png |
| `df -h` | Check the disk size of the root (/) file system | disk-check.png |
| `top` | See the running processes and CPU load | - |
| `docker run -d --name client-website -p 8080:80 nginx` | Start the Nginx container and connect port 8080 to port 80 | install-nginx.png |
| `docker ps` | Check if the container is running | install-nginx.png |
| `ss -tlnp \| grep 8080` | Check if something is listening on port 8080 | - |
| `curl http://localhost:8080` (3 times) | Send successful requests (HTTP 200) | simulation1.png |
| `curl http://localhost:8080/hidden-admin-page` | Request a page that does not exist (HTTP 404) | simulation2.png |
| `docker logs client-website` | See the request logs of the application | docker-logs.png |
| `docker logs client-website 2>&1 \| grep 404` | Filter the logs to show only the 404 line | - |
| `docker stats --no-stream` | View live CPU, memory, and network usage of the container | container-metrics.png |

## Skills Learned

- Using native Linux tools (`free`, `df`, `top`) to establish a host performance baseline
- Deploying a containerized web server and mapping host ports to container ports
- Simulating realistic and erroneous web traffic with `curl`
- Extracting and filtering container logs to isolate specific HTTP status codes
- Reading real-time container resource metrics with `docker stats`
- Translating raw system output into clear, documented evidence for a technical report

## Files

- [system-baseline-report.md](system-baseline-report.md)
- [container-observability.md](container-observability.md)
- [reflection.md](reflection.md)
- [screenshots/](screenshots/)
