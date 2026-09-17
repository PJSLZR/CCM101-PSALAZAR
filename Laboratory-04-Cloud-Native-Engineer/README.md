# Laboratory 4: Cloud-Native Engineer

## Mission Overview

This laboratory helped me understand the difference between Virtual Machines and containers. I used KillerCoda to practice Docker commands and deploy an Nginx web server.

## Objectives

* Understand VMs and containers
* Use Docker CLI commands
* Deploy an Nginx container
* Learn Docker port mapping
* Manage the container lifecycle
* Document the activity using Markdown

## Docker Commands Executed

### Checkpoint 3

```bash
docker --version
docker info
```

### Checkpoint 4

```bash
docker pull nginx
docker run -d -p 8080:80 --name my-nginx nginx
curl http://localhost:8080
docker ps
```

### Checkpoint 5

```bash
docker stop my-nginx
docker ps -a
docker rm my-nginx
```

## Skills Learned

I learned how to use Docker to pull images, run containers, check their status, stop them, and remove them. I also learned that `8080:80` connects the host port 8080 to the Nginx container's port 80.

## Challenges Encountered

At first, I felt confused about Docker commands, especially the `-p 8080:80` port mapping. I was also unsure about the difference between stopping and removing a container. After practicing, I understood the commands better. I felt relieved and happy when Nginx worked successfully because I could see the result of what I had done. Overall, the lab was challenging but satisfying, and it made me more interested in learning Docker and cloud technologies.
