# Mission Reflection

Object storage is better suited for storing millions of photos than a traditional block storage drive because it is built for scale. Block storage splits data into fixed-size blocks attached to a single server, which works well for operating systems and databases but becomes hard to manage and expensive when handling millions of separate files. Object storage keeps each photo as an object with its own metadata and unique ID in a flat structure, so capacity can grow almost without limit and files can be reached over HTTP through an API.

Docker made deploying MinIO much easier because I did not have to install or configure the software by hand. A single docker run command pulled the image, started the container, mapped ports 9000 and 9001, and set the login credentials through environment variables. The same command would work on any machine with Docker, which makes the setup fast and repeatable.

In cloud storage, a bucket is a top-level container that holds objects, similar to a folder at the root of the storage system. Each bucket has a unique name, and access rules and settings are applied at the bucket level. In this lab, I created client-photos to hold the client's uploaded images.

I think large enterprises prevent data loss by replicating data across multiple drives, servers, and even data centers or regions. Techniques such as erasure coding and replication mean that if one physical server crashes, the objects can still be rebuilt or served from another copy. Regular backups and versioning add another layer of protection.

My confidence with the Linux command line is growing steadily. Running docker commands, checking containers with docker ps, and managing files with git in a terminal now feels more natural than in earlier labs. I still look up options sometimes, but I understand what each part of a command does and can troubleshoot basic errors.
