# Laboratory 8: The Cloud Security Engineer

## Mission Overview

As part of the Cloud Security Team at CloudNova Technologies, I secured an exposed Ubuntu server that was hosting a client's web application with no firewall configured. I deployed the vulnerable Nginx application, audited and locked down the server using UFW (Uncomplicated Firewall) with a strict default-deny policy, and selectively allowed only SSH and port 8080 traffic so the application remained reachable while every other port stayed closed.

## Objectives

- Understand the concept of the Attack Surface and the Principle of Least Privilege (PoLP).
- Perform a basic security audit of active network ports on a Linux server.
- Configure the Uncomplicated Firewall (UFW) with a Default Deny policy.
- Implement granular port management to selectively allow SSH and HTTP traffic.
- Document firewall rules and security best practices using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

## Commands Executed

| Command | Purpose | Evidence |
|---|---|---|
| `docker run -d --name secure-web-app -p 8080:80 nginx` | Deploy the vulnerable Nginx web application | vulnerable-app-running.png |
| `docker ps` | Confirm the container is running | vulnerable-app-running.png |
| `curl http://localhost:8080` | Verify the application is reachable before securing the server | vulnerable-app-running.png |
| `sudo ufw allow ssh` | Permanently allow SSH (port 22) so the server stays administrable | firewall-activated.png |
| `sudo ufw default deny incoming` | Block all incoming traffic by default | firewall-activated.png |
| `sudo ufw default allow outgoing` | Allow all outgoing traffic by default | firewall-activated.png |
| `sudo ufw enable` | Activate the firewall with the above rules | firewall-activated.png |
| `sudo ufw status verbose` | Confirm the firewall is active with the default deny policy | firewall-activated.png |
| `sudo ufw allow 8080/tcp` | Explicitly allow web traffic on port 8080 | firewall-port-allowed.png |
| `sudo ufw status numbered` | Verify the new rule was added to the firewall list | firewall-port-allowed.png |
| `curl http://localhost:8080` | Prove the application is still reachable after the firewall is active | firewall-port-allowed.png |

## Skills Learned

- Understanding the Principle of Least Privilege and how it applies to cloud accounts and services
- Identifying and reasoning about a server's attack surface
- Configuring a host-based firewall (UFW) with a default-deny security posture
- Performing granular port management to allow only required traffic
- Recognizing the correct order of operations when enabling a firewall remotely (SSH-first) to avoid self-lockout
- Documenting security configurations clearly for other engineers

## Files

- [security-audit-report.md](security-audit-report.md)
- [firewall-configuration.md](firewall-configuration.md)
- [reflection.md](reflection.md)
- [screenshots/](screenshots/)
