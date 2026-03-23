Before doing hardening on our system, you need to know 3 basic things:

1. exact Linux version: each version has different security policies, different services enabled by default, different kernel versions, and system configurations that change. - [Kernel](../../Notes/00-Preflight-INotes.md.md#kernel)

2. machine name: the machine to which the hardening will be applied

3. IP address (IP)
-[Commands](../../Notes/00-Preflight-INotes.md.md#Commands)


When you type **ip a** :

![](attachments/Pasted%20image%2020251223155744.png)

several things appear that we need to take into account:

**lo**:  [loopback](../../Notes/00-Preflight-INotes.md.md#loopback) interface. This one can't be atacked, as isn't exposed out on the network.
**ens33**: is the actual [interface](../../Notes/00-Preflight-INotes.md.md#Wi-Fi_Interface) (the one that goes out to the network).  It's a virtual network interface that VMware provides to my machine.


### Chronological Analogy

TRAFFIC  ⇨ AIRPORT (ens33) ⇨ Passport control (fw) ⇨ CITY (my ubuntu system)



