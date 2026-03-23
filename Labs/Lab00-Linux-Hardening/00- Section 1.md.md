### Section 1 - Update and patch the system

The first we'll do in this lab is check if our Ubuntu system has :
- the latest security patches
- Up-to-date versions of **critical packages:** this critical packages, are system components that, if it fails or has a vulnerability, can compromise the entire system. E.g., kernel, OpenSSH (the software that implements the SSH protocol), OpenSSL, or systemd.
- Fixes for Common Vulnerabilities and Exposures (CVE). CVE= A known and identified security flaw. E.g., CVE-2024-3094 → identifies malware when entering at xxxxx.net website.

Why are  these 3 points so important?  More than 80% of successful attacks on companies occur due to failing to follow these 3 points. Attackers exploit outdated machines. 

[Commands](00-Section_1-INotes.md#Commands)

Once executed, we must perform a  <span style="color: red;">sudo reboot </span>: when updating major components (systemd, [drivers](../../Notes/00-Section_1-INotes.md.md#Drivers), etc.), it is recommended to restart the operating system.  

