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
Basic fixed password for Docker public repository from marchandd/term_ssh_user_monodotnet45 image = 'term_ssh_user_monodotnet45'

:computer: `ssh -X docker@XXX.XXX.XXX.XXX -p YYYYY`

### Alias

When you are into SSH access.

:computer: `monodevelop`

## Explanations

### Dockerfile

All details on [parent image](https://github.com/marchandd/term_ssh_user_monodotnet45/ "Parent")

- Download MonoDevelop from Xamarin.
- Download MonoDevelop-nunit from Xamarin.

### Display

Make sure to have installed OpenSSH client or GUI SSH client (Putty).

### Risks

A password is used and not a certificate that could be more secure.
 