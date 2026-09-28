# MinIO Deployment

## Deployment command

Run this command in the KillerCoda Ubuntu playground. It starts MinIO in the background, publishes the S3 API on port `9000` and the web console on port `9001`, and sets the root login credentials for this lab:

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
  -e "MINIO_ROOT_USER=cloudadmin" \
  -e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
  minio/minio server /data --console-address ":9001"
```

The `-e` flags pass environment variables into the container. `MINIO_ROOT_USER` sets the MinIO root username, and `MINIO_ROOT_PASSWORD` sets its root password. These credentials are provided by the lab and are for this temporary exercise only; do not reuse them in production or expose them in a public repository.

## Verify and connect

Check that the container is running:

```bash
docker ps --filter name=minio-server
```

Open port `9001` through KillerCoda's Traffic/Ports or Custom Ports interface to reach the MinIO web console. Sign in with the lab credentials above. Port `9000` is the S3-compatible API endpoint.

## Bucket and upload

In the console, open **Buckets**, create a bucket named `client-photos`, enter it, and upload a safe sample image or text file. The bucket name and uploaded object should be visible in the console afterward.

## Evidence

Save genuine screenshots from the playground in the `screenshots/` folder:

- `minio-deployed.png` — terminal showing the running MinIO container.
- `minio-bucket-upload.png` — console showing the `client-photos` bucket and uploaded object.

These screenshots have not been captured in this workspace. Add them after running the deployment in KillerCoda; do not use fabricated evidence.

