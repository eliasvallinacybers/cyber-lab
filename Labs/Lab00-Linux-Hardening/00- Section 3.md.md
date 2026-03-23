## 3.1 SSH hardening (secure configuration)

Before making any changes to harden the system, we first need to check out its current status to see what is being used and avoid touching things that might affect the server services (that users access over SSH).

This way, I'm going to access to this directory : /etc/ssh/sshd_config. This is the ssh server (sshd) main file, where its configuration is located : [(1)](00-Section_3-INotes.md#Commands)

We press Ctrl + W and search for:
1. port 22
2. passwordAuthentication
3. permitrootLogin

1.
![](attachments/Pasted%20image%2020260106113211.png)

We can see SSH is using the default port, which is 22.



2.
![](attachments/Pasted%20image%2020260106114714.png)
The SSH server allows users to log in using password authentication.


3.
![](attachments/Pasted%20image%2020260106113910.png)

'permitRootLogin' indicates that [root](00-Section_3-INotes.md#Root) is allowed (permit) to log-in (Login). However, 'prohibit-password' specifies that password authentication is not a method allowed for root to log in.

Root is discussed a lot in SSH because if we allow direct root login, an attacker already knows the username (root) and only needs the password. That’s why hardening usually disables root SSH login and uses a normal user account, relying on `sudo` only when admin privileges are needed.




## 3.2 Change the SSH port

I change the default SSH port (22) to a non-default port. I choose 2222. Thus, all the automatic bots, that might attempt to access the default port, won't success, as now our server is no longer listening it.

When changing to 2222 port, we go more unnoticed, as the attacker will need to perform a deeper scan to find the port our SSH server is listening on.

**Note**: Only the ports that are opened in the firewall will be exposed to the network. This exposed ports are the ones that might be attacked.


### Visual schema

![](attachments/Pasted%20image%2020260106145947.png)

This schema is a easy way to understand what's happening:

Users (represented as cars) detect an open port on a specific server. Those who are interested in accessing it, head towards that port until they hit the server's firewall. 

The firewall is the responsible of allowing or denying access to that port, according to a set of predefined rules, aimed at protecting the server.

If a user is allowed to pass through the firewall, it will be able to attempt to access the server listening on that port. If the user logs in successfully, they have gained access to the server.

**Note :** not open port → no visible port on the network → no attempts to access this port.

**Note 2:** Although clients can technically attempt to connect to a non-visible port, the firewall will not allow the traffic through. As a result, in practice, clients will not even bother trying.

**Note 3:** Do not confuse two different things. **Port “X” being open (on the firewall) to the Internet ≠ the server is listening on that port**.  
If port “X” is open, it simply means that the firewall will allow traffic from clients directed to that port.  
However, if that server is not listening on that port, the client will attempt to connect to the server’s (public) IP through port “X”, but it will not receive any response, since the server was not listening on that port.


### Administrative Access Hardening (Root Login vs sudo)

When users access the system directly as root over SSH, they are granted full administrative privileges. In this scenario, there is no intermediate level of access: anyone who can log in as root has complete control over the system. Revoking this access usually requires changing the root password, removing SSH keys, or disabling the root account, which affects all administrators.

By contrast, using a regular user account with sudo allows administrative privileges to be assigned on a per-user basis. Users authenticate with their own accounts and only elevate privileges when required. If a user should no longer perform administrative tasks, sudo access can be revoked without blocking SSH access or modifying the root account. This approach provides better control, traceability, and flexibility in privilege management.

On the other hand: disabling password-based authentication prevents brute-force attacks against SSH. To do this, I remove password login as a valid authentication method. As a result, access to the server is restricted to users who possess a valid SSH key, which significantly strengthens authentication security. This configuration is considered a fundamental hardening measure and reflects industry best practices for secure remote access.







