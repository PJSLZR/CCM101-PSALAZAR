# Research: Types of Cloud Storage

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| **Block Storage** | Splits data into fixed-size blocks, each with its own address. Attached to a single server like a virtual hard drive. | Operating systems, databases, and workloads needing low-latency, high-performance disk access. | AWS EBS (also Azure Managed Disks, Google Persistent Disk) |
| **File Storage** | Stores data as files in a hierarchy of folders and directories, shared over a network using protocols like NFS or SMB. | Shared drives, content management, home directories, and applications where many servers need the same files. | AWS EFS (also Azure Files, Google Filestore) |
| **Object Storage** | Stores each piece of data as an object with its own metadata and unique ID in a flat structure, accessed over HTTP via an API. | Massive amounts of unstructured data such as images, videos, backups, and logs. | AWS S3 (also Azure Blob Storage, Google Cloud Storage) |

## Why Object Storage for the Client's Photos

Object Storage is the best choice for your photo-sharing application because it scales to millions of images without you having to manage disks or capacity. Each photo is stored as an independent object with its own metadata and can be uploaded or served directly over HTTP through an S3-compatible API. Unlike a block volume tied to one server or a file share that struggles at this scale, object storage is durable, cost-effective, and independent of any web server container.
