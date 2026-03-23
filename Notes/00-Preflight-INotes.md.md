./Obsidian-1.10.6.AppImage --no-sandbox

### kernel
= the brain of the OS (Operating System). It manages hardware, memory, processes, and security.

- Its version indicates the level of patches and capabilities.
- In hardening, the first thing you need to check is the kernel and update it to avoid vulnerabilities.

**Note**: patches = updates/fixes used to update and correct software issues, vulnerabilities, etc.

### Commands

1. <span style="color: red;">lsb_release -a </span>
2. <span style="color: red;">hostname </span>
3. <span style="color: red;">ip a</span>


### loopback 
= feedback loop.

The loopback interface is the monitor’s internal interface. It’s used so that programs inside the system (the computer itself) can communicate with each other. Example: one program asks another program on the same PC for information.


### Interfaces
= a point or path through which our OS sends and receives packets.

- There are loopback interfaces, Ethernet (cable), Wi-Fi, VPN, Docker/containers, etc. In this way, our OS decides where traffic will go out: “This will go out through Wi-Fi”, “This goes out through VPN”, “this through …”.

- Each interface has its IP address, mask, MAC (if it’s physical), MTU, and UP/DOWN state (= indicates whether that interface is enabled or not and therefore whether our OS can use that interface to send/receive traffic).

### Wi-Fi_Interface

- Every user has his own Wi-Fi interface (Wi-fi card). This is the one which has the IP adress. The user hasn't IP, is the user's interface who has the IP. of Example: 1- I send a WhatsApp message to Mom 2- She replies. Both messages go through the same interface (Wi-Fi). If my mother is out on the street, she will use for incoming and outgoing messages the mobile data interface (on Android often called rmnet_data0 or something like that). This rmnet_data0 has a different IP than the Wi-Fi  interface.

- All the traffic we send to the network goes through the Wi-Fi interface (destination point) ,  just as the traffic arriving at our firewall has arrived through it.






