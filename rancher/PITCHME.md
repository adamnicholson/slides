## Rancher!

### Software delivery evolution

---

### What I'm going to tell you

  1. Docker/container recap
  2. What does a container orchestrator do
  3. Deploying an app with Rancher (demo)

---

## Docker?!

> Docker is the world’s leading software container platform
>
> -- <cite>https://www.docker.com/what-docker</cite>

- Docker is a *Container* platform

---

## Containers?!

> A container image is a lightweight, stand-alone, executable package of a piece of software that includes everything needed to run it: code, runtime, system tools, system libraries, settings
>
> -- <cite>https://www.docker.com/what-docker</cite>


---

## So.. like virtual machines?

No. Topic for another day, but in short:

- VMs are whole operating systems with fixed resources; containers share resources
- Containers are optimally *single processes*, with *no state*
- If VMs are houses, containers are flats in apartment buildings

---

## Ok.. Why?!

In their (docker.com) own words:

> Developers use Docker to
> ...
> eliminate “works on my machine” problems
> ...
> manage apps side-by-side in isolated containers
> ...
> build delivery pipelines to ship features faster, more securely and with confidence

---

## How to Docker

1. Write some code
2. Package up your code as a Docker `image`
3.  Publish your `image` to a Docker repsitory
4. Pull and run the `image` onto other machines (and servers)

---

## How to Docker

1: Write some code

```
echo "Hello, world!" > src/index.html
```

---

## How to Docker

2: Package up your code as a Docker `image`

```
# Dockerfile
FROM nginx:stable
ADD ./src /usr/share/nginx/html
CMD ["nginx", "-g", "daemon off;"]
```

```
docker build -t my-app:latest .
```

---

## How to Docker

3:  Publish your `image` to a Docker repsitory

```
docker push my-app:latest
```

---

## How to Docker

4: Pull and run the `image` onto other machines (and servers)

```
docker pull my-app:latest
docker run -p 80:80 my-app:latest
```

---

## You just learned Docker!

![You are so clever!](https://img.4plebs.org/boards/pol/image/1458/00/1458008739837.jpg)

---

## Next! Go-live!

---

## Going live with Docker
### The naive way

- Build & push your image
- Manually SSH to server, pull & run it
- Write some bash scripts to do that

For your personal blog, you should probably just do this.

---

## When the thing you are building is important

What we need to achieve:

- Availability:
  - Zero downtime deployments
  - Easily scalable
- Reliability:
  - Handle failures

---

---

## Container orchestration?!

> Kubernetes also allows developers to (move) from a host-centric infrastructure to a container-centric infrastructure,
>
> -- <cite>https://kubernetes.io</cite>

---

## Container orchestration?!

- Deploying and upgrading
- Checking application health
- Networking between services and the outside world
- Distributing secrets
- Balancing loads

---
