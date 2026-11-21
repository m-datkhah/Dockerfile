

## 📌 About the Project

The goal of the project was to create an Ubuntu image with SSH installed.

## ✨ Features

Creating an Ubuntu image using Docker
Running an SSH service on Ubuntu
Documenting installation steps and troubleshooting
Ready for use in a DevOps environment

Check for installation:

```bash
docker --version
docker compose version
git --version
```

Build the image using the following command:

```bash
docker build -t myubuntu-ssh .
```

Run the container using the following command

```bash
docker run -d \
  -p 2222:22 \
  --name ubuntu-ssh \
  myubuntu-ssh
```


## 📁 Project structure

```text
project/
├── Dockerfile
├── sshd-hardening.conf
└── README.md
```

## 📚 Things I learned

The root user is disabled by default in Ubuntu. To enable the root user, follow the steps below:
Create a file named 'sshd-hardening.conf' alongside the Dockerfile and add the content 'PermitRootLogin yes' to it.
In the Dockerfile, file 'sshd-hardening.conf' is copied to the path '/etc/ssh/sshd_config.d/00-enable-root-password.conf'.
The SSH command must be used exactly as follows:
    
    ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null root@172.17.0.1 -p 2222


## ⚠️ Errors and solutions


