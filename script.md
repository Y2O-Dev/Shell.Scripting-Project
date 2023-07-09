# Automate Deployment of a Website Template on Ubuntu Server with Apache2 using Bash Scripting

## Prerequisites
1. An AWS Ubuntu server with SSH access
2. Basic knowledge of Linux command line

## Step 1: Connect to the Ubuntu Server
- There are several ways to connect to a remote server. In this project, I created a *config* file within the **/.ssh** directory.
- I populated it with as follows:
> - Host: Any name of your choice (I named it webscript)
> - HostName: The Public IP of the instance
> - User: I used Ubuntu because its the default 
user given to  the server by AWS
> - Port: I did not add the port block because the SSH default port is 22
- On the terminal, I only need few commands to gain access to my server:

> `ssh webscript`

## Step 2: Writting The .sh File
- Using the vi editor:
> - Open a new file with a choice name and .sh extension. In my case, I gave it *webscript.sh* and open it with:
> `vi webscript.sh`
