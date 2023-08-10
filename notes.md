Links:

https://dockerhub.io/

https://docs.docker.com/engine/reference/commandline/run/

https://docs.docker.com/compose/

---

Unterschied VMs vs. Container
top-down view Docker Engine (aus K8s Präsi)

Docker Engine
Docker Daemon
Docker Client
Docker Registry
API Calls Build Pull Run

Dockerfile
Docker Image
Docker Container

Docker Compose

Volumes
Portbinding

---

Demo-Dockerfile:
S:
Alpine
cmd: echo "Hello Boys"

L:
Nginx-Alpine
Security
Docker Compose + Imperativ:
Volume: HTML File "Hello Boys"

https://hub.docker.com/_/nginx

---
commands:

cd small
docker build . -t docker-demo-s:1.0
docker run docker-demo-s:1.0

cd ..
cd large
docker build . -t docker-demo-l:1.0
docker run docker-demo-l:1.0

docker run -v ./html2:/usr/share/nginx/html:ro -d docker-demo-l:1.0

docker compose up