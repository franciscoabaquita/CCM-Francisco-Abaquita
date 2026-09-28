# Mission Reflection

Object storage is better suited to millions of photos than a traditional block-storage hard drive because it is designed to hold large amounts of unstructured data and scale across many objects. A block volume behaves like a disk attached to a server: the server manages its filesystem, and increasing capacity or sharing it can require additional administration. With object storage, each photo is stored as an object with its own key and metadata in a bucket. The application can keep the object's key and retrieve the image when needed, instead of tying the image to one web server's local disk.

Docker makes deploying MinIO easier because the server and its runtime are packaged in a container image. A single command downloads the image if needed, starts the service, sets its configuration through environment variables, and maps the API and console ports. This avoids manually installing and configuring the storage server and makes the deployment steps repeatable.

A bucket is a logical container for objects. It provides a place to organize related data and a scope for naming, access policies, and lifecycle settings. In this scenario, `client-photos` groups the photo objects for the application.

Large enterprises reduce the risk of losing data when a physical server fails by distributing redundant copies across separate disks, servers, or availability zones. They also use erasure coding, health monitoring, repair processes, versioning, and backups or replication to another region. Redundancy is not a replacement for backups, and recovery plans should be tested.

Working through the Linux command line helps build confidence because commands become more familiar with practice. In this lab, commands such as `docker run` and `docker ps` connect configuration with observable results. Running the steps in a disposable playground also provides a low-risk way to learn how ports, containers, and service logs fit together. After completing the deployment and checking the console, I can better understand how to troubleshoot a containerized service.

