### SSH 
= Secure Shell. 

is essentially a secure way to open a terminal on another computer over a network., i.e provides a secure remote shell session on another machine.

A shell is the command interpreter (e.g., bash). 
in this context, 'secure' means that communication in this session is **encrypted**, so no one can read your commands, passwords, or data even if the network is intercepted, and **authentication** is used to verify the identity of both the user and the remote system.

In practice, SSH allows us to **remotely access servers or virtual machines**, **administer and maintain them** (users, services, logs, and updates), **without physical access and in a secure manner**.





### SSHserver
= program that makes it possible for us to use SSH. "server," in SSHserver, indicates that its function is to allow other devices to connect to my machine (via ssh).

### Commands

(1) <span style="color: red;">systemctl status ssh</span> 
(2) <span style="color: red;">sudo apt install openssh-server</span> 
(3) <span style="color: red;">sudo systemctl enable ssh</span> 
(4) <span style="color: red;">sudo systemctl start ssh</span> 



### Daemon
= program always running in the background.


### ssh.service,ssh.socket

Both ssh.service and ssh.socket **are systemd units**—either of the service or socket type—which we will call the 'managers': **they start and manage the ssh daemon** (== sshd == ssh server). 

If we activate **ssh.service**, systemd keeps sshd always active. However, if we activate **ssh.socket**, systemd will only activate sshd when there is an incoming connection. 

This way, **in ssh.service, sshd is listening to the port all the time**, whereas **in ssh.socket, systemd is the one listening** (and i**t will wake up sshd** when there is an incoming connection).

Note: active != listening. However, when it comes to SSH, if it's active, directly or indirectly will be listening. 

Correct states:

**ssh.socket → active (listening)**. A socket cannot be running. Sockets listen.

**ssh.service → active (running)**. A service cannot be listening. That's for types like sockets, etc.. Despite of systemd being running, that implies that keeps sshd listening continuosly, so indirectly it's listening.







