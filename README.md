# marchandd/term_ssh_user_monodevelop

marchandd/term_ssh_user_monodevelop [Docker:copyright:](https://docs.docker.com/ "Docker") image

## Description

A sandbox container with last version of Mono environment ready to be exploited for Mono app from Linux or Windows host.  
This image contains also included Xamarin:copyright: monodevelop, last version of Mono environment IDE ready to use.

### Goal

Based from term_ssh_user_monodotnet45 image:  
Easy method to produce a terminal containers to run Mono app into sandbox from secured host to remote client with SSH.  
This image included Xamarin:copyright: mono-complete installed to run Gtk# and PCL (.Net Portable) apps.  
This image also included Xamarin:copyright: monodevelop and MonoDevelop-nunit (test usage) installed to create mono apps.

### Image size

Around 1000 Mb.

### References

[Marchand D. Maintainer](https://github.com/marchandd/ "Maintainer")

[Details source](https://github.com/marchandd/term_ssh_user_monodevelop/ "Details")

[Image parent](https://github.com/marchandd/term_ssh_user_monodotnet45/ "Parent")

[Part of project studies](https://github.com/marchandd/docker_index/ "References")

## Build image

### Command line

:computer: `docker pull marchandd/term_ssh_user_monodevelop`

### Command line explanation

All details on [parent image](https://github.com/marchandd/term_ssh_user_monodotnet45/README.md "Parent")

3 methods to find password:

- Search password value into build.log file from marchandd/term_ssh_user_monodotnet45 image to access later to container.

- If you don't have build image with log file redirection, use this comand:  
:computer: `docker inspect IMAGEID`

- If you don't have password value, enter directly into container to find log inside with [Nsenter](http://itsagooddaytobegeek.com/docker-ep-02-installation-de-nsenter/ "Nsenter")

### Firewall

:warning: If your Firewall is enabled on the host, with default outgoing policy turned to 
deny, 
you will have to disable 22 port filtering:  
- Make a new rule for OpenSSH (22/TCP) to enable outgoing policy.

## Build container

### Command line

:computer: `docker run -d -p XXX.XXX.XXX.XXX:YYYYY:22 marchandd/term_ssh_user_monodevelop`

Where XXX.XXX.XXX.XXX is your IP v4 address.  
Where YYYYY is your Private port, if you doesn't know free port, try from 49200...

### Command line explanation

- Run in detached mode.
- Export port 22.

## Container usage

### SSH access

Open terminal with docker account.

:computer: `ssh -X docker@XXX.XXX.XXX.XXX -p YYYYY`

### Alias

When you are into SSH access.

:computer: `monodevelop`

## Explanations

### Dockerfile

All details on [parent image](https://github.com/marchandd/term_ssh_user_monodotnet45/README.md "Parent")

- Download MonoDevelop from Xamarin.
- Download MonoDevelop-nunit from Xamarin.

### Display

Make sure to have installed OpenSSH client or SSH GUI client (Putty).

### Risks

A password is used and not a certificate that could be more secure.
 
## Linux test environment remote client

### SSH client terminal

- KUbuntu (14.10)
- Docker (1.4.1)
- ssh  
  Address -X docker@IPv4 -p PORT

## Windows test environment remote client

### SSH client GUI

:warning: Make sure X11 forwarding is enabled into SSH/X11 Configuration.

- Windows (7 & 8.1)
- Boot2Docker (1.4.1)
- VirtualBox (4.3.20)
- MsysGit (1.9.4)
- PuTTY (0.64)  
  Address Boot2Docker_IPv4:PORT

Remark:  
Docker is accessing on Windows only through VirtualBox network interface. 
So, using 127.0.0.1 is not possible...  
- You must choose Boot2Docker_IPv4 remained at boot start into the dedicated console.
