## Prerequisites
- Docker installed
- Internet access (for initial download)
- Storage medium to transfer the image

## 1. Pull the Docker Image
On a machine with internet access, run:
```bash
docker pull caddy:latest
```

## 2. Save the Image to a File
Export the image to a `.tar` archive:
```bash
docker save -o caddy_latest.tar caddy:latest
```

## 3. Transfer the Image
Move the `caddy_latest.tar` file to your offline environment using any method (USB, SSH, etc.).

## 4. Load the Image Offline
On the offline machine, run:
```bash
docker load -i caddy_latest.tar
```

## 5. Verify the Image
Ensure the image is available:
```bash
docker images
```
You should see `caddy:latest` listed.

## Usage
Run Caddy with the following command:
```bash
docker run -d --name caddy -p 80:80 -v /path/to/site:/usr/share/caddy caddy:latest
```
