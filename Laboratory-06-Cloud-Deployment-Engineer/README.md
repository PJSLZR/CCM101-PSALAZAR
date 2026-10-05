# Laboratory 6: The Cloud Deployment Engineer

## Mission Overview

As part of the Cloud Deployment Team at CloudNova Technologies, I deployed a proof-of-concept two-tier Nextcloud private cloud storage environment using Docker Compose. The stack consists of a MariaDB database container and a Nextcloud web application container, defined declaratively in a single `docker-compose.yml` file and deployed with one command.

## Objectives

- Explain the concept of a multi-tier application architecture.
- Understand the purpose and structure of a docker-compose.yml file.
- Use a Linux command-line text editor (nano) to create configuration files.
- Deploy a multi-container application (Nextcloud + Database) using Docker Compose.
- Document deployment procedures and Infrastructure as Code (IaC) principles using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

## Commands Executed

```bash
mkdir -p work/nextcloud-deployment
cd work/nextcloud-deployment
nano docker-compose.yml
docker-compose up -d
docker-compose ps
docker-compose down
```

## Skills Learned

- Designing and explaining a two-tier application architecture
- Writing a valid, properly indented docker-compose.yml file
- Using environment variables to configure linked containers
- Deploying and tearing down a multi-container stack with one command
- Understanding container-to-container DNS resolution within a Compose network
- Comparing imperative (`docker run`) and declarative (Docker Compose) deployment approaches

## Files

- [multi-tier-architecture.md](multi-tier-architecture.md)
- [docker-compose-guide.md](docker-compose-guide.md)
- [reflection.md](reflection.md)
- [screenshots/](screenshots/)
