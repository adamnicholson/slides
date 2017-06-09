## Rancher!

### Software delivery evolution

---

### First, a history lesson.

The year is 2005. 

You've built your first website.

How do you get it "live"?


---

## Back to the dark ages

### <span style="color: #e49436">Shared hosts and FTP</span>

> Well, how else am I supposed to do it?

---

### <span style="color: #e49436">Shared hosts and FTP</span>

1. Pay Company Co. for space on a shared server
2. Upload files via FTP
3. Point your domain at the server
3. Profit

### But..

- Sharing resources with other organisations sucks
- The server doesn't have everything installed I need

---

### <span style="color: #e49436">Dedicated & virtual servers</span>

> I know how to do Linux!

---

### <span style="color: #e49436">Dedicated & virtual servers</span>

1. Buy a VPS somewhere
2. Install PHP/nginx/whatever you like
3. Upload your app over SFTP 

---

```bash
$ ssh root@123.145.167.189
Welcome to Ubuntu 16.04.1 LTS (GNU/Linux 4.4.0-38-generic x86_64)

$ sudo apt-get install nginx php5-fpm php5-mysql
$ curl localhost
hello, world!
```

---

### <span style="color: #e49436">Dedicated & virtual servers</span>

#### **BONUS POINTS**
##### Use Vagrant and configure it the same as the server

---

### <span style="color: #e49436">Dedicated & virtual servers</span>

- Control over the server
- Improved performance
- Like, security!

---

### Then...

- Infrequent, big-bang deploys are a PITA
- Do we really need to take the site down for a deploy?

---

#### Facebook told us to "move fast and break things"

#### We need faster and easier deploys!

---

### <span style="color: #e49436">Scripted git-based deployments</span>

1. Get a tool like Capistrano, Deployer, or write some bash scripts
2. Tell it how to build your app
3. Point it at your server

---

```bash
$ cap production deploy
```

#### This must be it! 
#### How could things be any better?!

---

### <span style="color: #e49436">Scripted git-based deployments</span>

- No more downtime on deployments!
- We can deploy whenever we like at the tap of a key!

---

## What could there possibly be left to solve?!

- Why do we still have differences between dev (Vagrant) and production?
- What happens when something falls over in production?
- How do you scale out to more servers?
- How do we add to our tech stack?


---

### Where next?

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
