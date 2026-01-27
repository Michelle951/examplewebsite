---
title: "EN Example"
description: "Resources needed before deploying an application in Kubernetes."
image: "https://api.dicebear.com/9.x/glass/svg?seed=Alexander"
startDate: "2025-11-09"
skills: ["Kubernetes", "Container Image", "Appliaction Deployment"]
---

[Kubernetes](https://kubernetes.io/docs/home/) is a production‑grade container orchestration system that automates deployment, scaling, and management of containerized applications.It runs on cloud providers or on‑premises, integrates with container runtimes (containerd, CRI‑O, etc.), and has a rich ecosystem (Helm, Operators, Ingress controllers, CNI plugins, Prometheus, etc.). In Kubernetes, applications run as images in containers This article will shows you how to make a container image.

## Prerequisites

- Ensure Docker is installed on your system.
- Prepare application source codes. Use your own codes or clone a public Git project. For example:

  `git clone https://github.com/nigelpoulton/qsk-book.git`

## Steps:

1. Add a Dockerfile in the root directory of your codes. A Dockerfile contains commands for building application codes into an image. It is essential for containerization. Here is an example:

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

2. Run this command in the directory with the Dockerfile to build the image.

   ```bash
   docker image build -t [your_docker_id]/[your image:version] .
   ```

   Note: Do not miss the period at the end. It indicates the context path, which includes all files in the specified directory. Avoid unnecessary files in this context to prevent slow builds.

3. Upload the image to your image registry.

   `docker image push <your_docker_id>/<your_image_name:version>`

**[TO be continued...]**
