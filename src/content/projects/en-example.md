---
title: "EN Example"
description: "Resources needed before deploying an application in Kubernetes."
image: "https://api.dicebear.com/9.x/glass/svg?seed=Alexander"
startDate: "2025-11-09"
skills: ["Kubernetes", "Container Image", "Appliaction Deployment"]
---

[Kubernetes](https://kubernetes.io/docs/home/) is a production‑grade container orchestration system that automates deployment, scaling, and management of containerized applications.It runs on cloud providers or on‑premises, integrates with container runtimes (containerd, CRI‑O, etc.), and has a rich ecosystem (Helm, Operators, Ingress controllers, CNI plugins, Prometheus, etc.). Before using Kubernetes, applications must be packaged as container images and a cluster provisioned — the following section covers preparing a container image.

## Preparation

Kubernetes(K8s) is designed for managing containers, which encapsulate an application and its dependencies into a portable package, stored as a container image. You can obtain a container image in two ways:

- Use any existing images from a public repository like [Docker Hub](https://hub.docker.com/).
- Build your own image and push it to your online repository with following steps, if you prefer the hardway.

Steps to build a container image:

1. Ensure Docker is installed on your system.
2. Prepare application source codes. Use your own codes or clone a public Git project. For example:

   `git clone https://github.com/nigelpoulton/qsk-book.git`

3. Add a Dockerfile in the root directory of your codes. A Dockerfile contains commands for building application codes into an image. It is essential for containerization. Here is an example:

   ```bash
   FROM node:current-slim
   LABEL MAINTAINER=nigelpoulton@hotmail.com
   COPY . /src RUN cd /src; npm install
   RUN cd /src; npm install
   EXPOSE 8080
   CMD cd /src && node ./app.js
   ```

   - FROM: Specifies the image for building (node:current-slim).
   - COPY: Copies application codes and dependencies to the `/src` directory in the `node` image.
   - RUN: Executes the command to install the dependencies.
   - EXPOSE: Lists the port that the application will listen on.
   - CMD: Defines the main application process to run when the container starts.

4. Run this command in the directory with the Dockerfile to build the image.

   ```bash
   docker image build -t [your_docker_id]/[your image:version] .
   ```

   Note: Do not miss the period at the end. It indicates the context path, which includes all files in the specified directory. Avoid unnecessary files in this context to prevent slow builds.

5. Upload the image to your image registry.

   `docker image push <your_docker_id>/<your_image_name:version>`

**[TO be continued...]**
