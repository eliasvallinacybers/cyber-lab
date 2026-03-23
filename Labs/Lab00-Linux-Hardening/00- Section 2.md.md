## SSH Hardening

What we will do now is check if we have [SSHsever](00-Section_2-INotes.md#SSHServer). [(1)](00-Section_2-INotes.md#Commands)

When executing, we can see the following:

![](attachments/Pasted%20image%2020251231115538.png)

As observed, 

First of all, I install the the [daemon](00-Section_2-INotes.md#Daemon) ssh (= sshd = ssh server)) package [(2)](00-Section_2-INotes.md#Commands). Next, what we want first of all is to activate that sshd we just installed. We can activate it by 2 different ways: 1- by [ssh.socket](00-Section_2-INotes.md#ssh.service,ssh.socket)  2- by [ssh.service](00-Section_2-INotes.md#ssh.service,ssh.socket) . The one that interests us most is the second, since in hardening we don't want to rely on automatic activation; it is more secure to set it to always active mode.
In this way, we execute the following two commands. The first one enables and the second starts ssh service. 

[(3)](00-Section_2-INotes.md#Commands)'enable' means that SSH is configured to start automatically when the system boots, whereas [(4)](00-Section_2-INotes.md#Commands) 'start' is a subtuype of  means starting `ssh.service` so that it is running at the moment.

As we wanted, the result is the following:
![](attachments/Pasted%20image%2020260105221353.png)

Q: But... Why we want ssh.service active constantly? ⇨ A: Otherwise, in the real world,  a real server (e.g cloud server) would be useless if at any time some users want to connect but they wouldn't make it (ssh.service status = dead).

Note: this lab focuses on real hardening.
