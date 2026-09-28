# Cloud Storage Types

| Storage type | Description | Primary use case | Cloud provider example |
|---|---|---|---|
| **Block Storage** | Stores data as fixed-size blocks on a volume that a server can format and manage as a disk. | Low-latency storage for operating systems, databases, and virtual machine disks. | Amazon Elastic Block Store (Amazon EBS) |
| **File Storage** | Organizes data as files in directories and exposes a shared filesystem, commonly through NFS or SMB. | Shared team folders, home directories, and applications that need a familiar filesystem interface. | Amazon Elastic File System (Amazon EFS) |
| **Object Storage** | Stores each item as an independent object containing the data, metadata, and a unique key in a flat namespace such as a bucket. | Large amounts of unstructured data, including images, videos, backups, and static website assets. | Amazon Simple Storage Service (Amazon S3) |

Object Storage is a strong fit for the client's user-uploaded images because it is designed to store large amounts of unstructured data and can scale independently of the web-server containers. Each image can be stored as an object and retrieved by its key, while the application stores the object's reference rather than keeping image files on an ephemeral server disk. A managed object-storage service can also provide durability and access controls suited to production workloads.

