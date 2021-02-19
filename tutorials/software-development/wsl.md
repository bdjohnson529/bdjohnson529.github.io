---
title: "Windows Subsystem for Linux"
layout: default
parent: SDE
parent_path: /tutorials/software-development/
---
Our apps will typically be deployed on Linux machines. To streamline deployment, it is recommended that the apps are tested on Ubuntu before attempting to deploy them on an external machine via Azure Pipelines or Azure App Service. Fortunately, Microsoft has released a contanerized version of Linux, called the Windows Subsystem for Linux, which can be installed on Windows machines. The WSL is available for installation through the Microsoft Store, free of cost. Surprisingly enough, the majority of Linux computers in the world are actually deployed by Microsoft, so they have plenty of experience containerizing the Linux OS.

## Ubuntu Installation
1. Install Ubuntu from the Microsoft Store.
2. Configure Windows to recognize the Windows Subsystem for Linux. There may be an additional step here.

After Ubuntu is intalled, you can enter the Ubuntu subsystem by launching the `Ubuntu` program. Notice that the filesystem in Ubuntu is intenionally separated from the Windows filesystem - you won't see any `Documents` or `Downloads` folders. If you haven't used Linux before, it's worth making your way through [Ubuntu's quickstart guide](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview) so that you can navigate the Linux command line.

## Sublime Text Installation
Presumably you will need some sort of text editor to edit your code. You can use VisualStudio, which reportedly has a nice integration with WSL2. I prefer to use Sublime Text, as it is a lighter application. To launch Sublime text from the Linux command line, you'll need to configure the `~/.bashrc` file, which defines aliases for the Linux command line.

First, make sure Sublime Text is installed on Windows. Likely it is installed at the following location : `C:/Program Files/Sublime Text 3/subl.exe`. You'll need to find where the Sublime executable lives, so that we can alias it in Linux. 

1. Launch Ubuntu.
2. Edit the `~/.bashrc` file.
```bash
sudo nano ~/.bashrc
```
3. At the bottom of the file, add the following line, where the path is the proper path to your sublime installation.
```bash
alias subl='/mnt/c/Program\ Files/Sublime\ Text\ 3/subl.exe'
```
4. Source the `bashrc` file.
```bash
source ~/.bashrc
```

Now you can launch sublime by typing `subl .` within any folder.

## Docker Installation
In addition to installing Ubuntu, we will need to install Docker, a utility which will containerize our application. Ultimately, we will be using [Buildpacks](https://buildpacks.io/docs/app-journey/) to generate the Docker image, but buildpacks needs an installation of Docker to communicate with. 

1. Install [Docker for Windows.](https://hub.docker.com/editions/community/docker-ce-desktop-windows/)
2. Check the WSL version of your Ubuntu distro. In the Ubuntu command line,
```bash
wsl.exe -l -v
``` 
3. If the version of your Ubuntu distro is 1, you need to upgrade to WSL2. To do this, set the version in Windows Powershell.
```bash
wsl --set-version Ubuntu 2
```
4. Follow the instructions on the [Docker website](https://docs.docker.com/docker-for-windows/wsl/) to add your Ubuntu distro as a Docker resource.
5. Test the docker installation. In Ubuntu:
```bash
docker run -d -p 80:80 docker/getting-started
```
And verify the app by accessing the following URL:
```bash
http://localhost
```
You can also see the app running in the Docker GUI.


## Add an SSH key for Azure DevOps
To clone repositories from Azure DevOps, you'll need to create an SSH key with WSL2, and add the key to your DevOps account. [Follow this tutorial.](https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops)


## Python virtual environments
Our app will also require Python virtual environments to run.
1. Install python3 venv
```bash
sudo apt-get install python3-venv
```


# Troubleshooting
If you're having trouble pinging `google.com` from the WSL, try the following. Edit `/etc/resolv.conf` and add the following nameserver:
```bash
nameserver 1.1.1.1
```


## Further Reading
* [Heroku Buildpack: Python](https://elements.heroku.com/buildpacks/heroku/heroku-buildpack-python)
* [Docker on WSL2](https://hinty.io/ivictbor/simple-way-to-docker-on-windows-10-home-with-wsl-2/)
* [Create a Running Docker Container With Gunicorn and Flask](https://medium.com/better-programming/create-a-running-docker-container-with-gunicorn-and-flask-dcd98fddb8e0)