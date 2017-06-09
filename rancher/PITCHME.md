## Rancher!

### Software delivery evolution

---

### First, a history lesson.

The year is 2005. 

You've built your first website.

How do you get it "live"?


---

## Shared hosts and FTP

### Back to the dark ages

> I've built my app - how do I deploy it to production?

1. Pay some company for space on a pre-configured shared server
2. Upload files via FTP
3. Profit

---

## Shared hosts and FTP

### Why we did it

- It was easy, and we didn't know any better

### Why it sucked

- Shared resources with other organisations
- Our applications depend on things you don't get on shared hosts
- Impossible to deploy without downtime

---

## Dedicated & virtual servers

1. Buy a VPS somewhere
2. Install PHP/nginx/whatever you like
3. Upload your app using FTP 

**BONUS POINTS**: Use Vagrant and configure it the same as the server

---

```bash
$ ssh root@123.145.167.189
Welcome to Ubuntu 16.04.1 LTS (GNU/Linux 4.4.0-38-generic x86_64)

$ sudo apt-get install nginx php5-fpm php5-mysql
$ curl localhost
hello, world!
```

---

## Dedicated & virtual servers

### Why this was good

- Full control over how the server was setup
- Improved performance over shared hosts
- More secure than sharing servers with randoms

---

## Scripted git-based deployments

> Doing FTP uploads, or manual git clones, is a pain..

1. Get a tool like Capistrano, Deployer, or write some bash scripts
2. Automatically git clone your resources to the server, build your app, then flip the new version on

---

```bash
$ cap production deploy
```

This must be it. How could things be any better?!

---

## Scripted git-based deployments

- No more downtime on deployments!

---

## What could there possibly be left to solve?!

- Why do we still have differences between dev (Vagrant) and production?
- What happens when something falls over in production?
- How do you scale out to more servers?
- How do we add to our tech stack?


---

### What's the answer?

---

![DOCKER](http://i.imgur.com/V9MhfBd.png)

### (or more specifically, Containers)

---

### For the uninitiated... Containers?

> A container image is a lightweight, stand-alone, executable package of a piece of software that includes everything needed to run it: code, runtime, system tools, system libraries, settings
> 
> -- <cite>https://www.docker.com/what-docker</cite>

- Docker is a *Container* platform


### Containers are not Virtual Machines

![Docker vs VM](https://i.imgur.com/MJHfm1c.jpg)
