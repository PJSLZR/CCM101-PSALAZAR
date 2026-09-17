# Mission Reflection

In this laboratory, I learned more about Docker and how it is different from using a Virtual Machine. For me, Docker is much faster to start because the container does not need to install a complete operating system. When I run a Docker container, it can start in only a few seconds. In a Virtual Machine, I need to install an operating system first and configure different settings before I can use it. Because of this, I think containers are more convenient when we need to deploy applications quickly.

The port mapping `-p 8080:80` is necessary because the web server is running inside the container. The port 80 is where Nginx is listening inside the container, while 8080 allows me to access it from the host machine. At first, I was confused about this part, but after using `curl http://localhost:8080`, I understand it better because I can see the Nginx response.

When I use `docker rm`, the container is removed from Docker. The data that is only stored inside the container can also be deleted. This made me realize that containers should not be depended on for important data unless we use volumes or another storage solution.

I think containerization can make developers and IT operations work more together because the application can run in a similar environment. Developers can create the container and operations teams can deploy the same container without setting everything again. It can make the process faster and reduce problems caused by different environments.

My GitHub portfolio is also slowly improving. Before, I mostly uploaded simple activities and codes. Now, I am learning to organize my projects, write README files, add reflections, and document the commands I used. I feel that my portfolio is becoming more complete and shows my progress as an IT student.
