# Docker Snort3

Unofficial [snort3](https://www.snort.org/snort3) IDS/IPS software docker image.

# Information
* From : Debian Bookworm Slim
* Size : 745 MB
* Time : Build from source. Take multiples minutes depending on your system
* Snort Version : 3.5.2.0
* Libdaq Version : 3.0.17
* Trivy : 0 unfixed vulnerabilities.

## How to build
```bash
$ docker build -t snort3:latest .
$ docker compose build
```

# Usage
To use file from your host:
* Create a directory in your home with the name `snort`
* Modify `docker-compose.yml`: replace `$USER` with your username in the volumes section
* Place the files you want in host: `/home/$USER/snort`
* In the docker container they are available at `/files`

## Example 1
```bash
$ docker compose run --rm snort3 -i eth0
```
## Example 2
```bash
$ docker compose run --rm snort3 -r /files/file.pcap
```

# Security
* Lint with [hadolint](https://github.com/hadolint/hadolint)
* Scan with [trivy](https://github.com/aquasecurity/trivy)

# To-Do
- [ ] Create and configure snort.conf file.
- [x] Add docker-compose.yml file.
- [x] Push image to Docker Hub.
