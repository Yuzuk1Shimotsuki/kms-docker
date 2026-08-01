# KMS-Docker

A self-hosted Microsoft's KMS server, in Docker Compose.

This compiles [vlmcsd](https://github.com/Wind4/vlmcsd) source code into a Docker image, which is useful for building a KMS server inside a containerized environment.

The project was designed to work with Docker Compose. However, you can also take it as a reference and build something else such as Kubernetes for your own purposes.

For more information such as the usage of vlmcsd, refer to their official [GitHub repository](https://github.com/Wind4/vlmcsd).

# Usage

### Direct Download

Pull the latest public image from **[packages](https://github.com/Hoshinowo-Yuki/kms-docker/pkgs/container/kms-docker%2Fstable)** session inside this repo:

```bash
docker pull ghcr.io/hoshinowo-yuki/kms-docker/stable
```

Then copy the `docker-compose.yml` file from this repo or create your own as follows:

```yaml
services:
  kms-docker:
    container_name: kms-docker
    build: .
    ports:
      - "1688:1688"
    restart: always
```

and run the following command to start the container:

```bash
docker-compose up -d
```

### Build from Source

Clone this repository and build the image from source:

```bash
git clone https://github.com/Hoshinowo-Yuki/kms-docker.git
cd kms-docker
docker build -t kms-docker .
```

and start the container inside the same directory when finished:

```bash
docker-compose up -d
```

# License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
