# Cloud Infrastructure Components

## 1. Compute Resources
Compute resources are responsible for running programs and processing commands. In my KillerCoda session, the `lscpu` command showed that I have 1 CPU core using an Intel Xeon processor. This means the server can handle basic tasks, but more CPU cores would be useful for applications with many users.

## 2. Storage Resources
Storage resources are used to save files, programs, and other data on the server. My `df -h` output showed a 19G disk mounted at `/`, with about 13G of available space. Storage is important because the server needs enough space for its operating system, applications, and user data.

## 3. Networking Resources
Networking resources allow the server to communicate with other computers and online services. My `hostname -I` command showed the IP addresses `172.30.1.2` and `172.17.0.1`. This network connection allowed my KillerCoda server to communicate with GitHub when I cloned and pushed my repository.

## 4. Operating System
The operating system manages the computer's hardware and allows programs and commands to run. My KillerCoda session uses Ubuntu 24.04.4 LTS. The operating system connects the compute, storage, and networking resources so they can work together properly.
