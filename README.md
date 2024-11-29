# Portfolio-2

## Aims
A sandboxed network provides an essential learning environment and platform, offering a secure, isolated space to simulate real-world network scenarios without introducing risks to live systems. For this Portfolio, you will create your own private sandboxed virtual network using VirtualBox. The network will consist of multiple virtual machines (VMs) configured within a private IP address range. The network will be isolated within a private IP address range and consist of the following key components:

* Router (Ubuntu Server): Manages the routing of network traffic between VMs.
* Desktop VM (Ubuntu Desktop): A client machine that communicates with both the router and the Application VM.
* Application VM (Bitnami WordPress): A server hosting an application (WordPress in this case).
  
The goal of the project is to demonstrate an understanding of network setup, IP subnetting, network interface configuration, and testing network functionality.

## Functional test

### Router: Ubuntu Server

#### Network Configuration:
On the router VM (Ubuntu Server), the primary network configuration file is /etc/netplan/50-cloud-init.yaml. This file contains the network settings for all adapters.

**Command: sudo nano /etc/netplan/50-cloud-init.yaml**

![network configuration-router](https://github.com/user-attachments/assets/9d8808ef-e121-4310-8415-cfbac0824fe1)

#### IP address of all adapters:
After configuring the network settings, you can verify the IP addresses assigned to each network interface on the router by using the following command:

**Command: ip a**

This command will display all IP addresses associated with the router’s network interfaces.

![ip adapter](https://github.com/user-attachments/assets/e4846848-05e3-409a-920e-c047e2fbadaf)

#### Pinging Desktop VM and Application VM:

**Command to ping Desktop VM: ping 192.168.116.1**

**Command to ping Application Server: ping 192.168.16.1**

![pboth](https://github.com/user-attachments/assets/21821048-10c4-413f-b073-1e7f53282099)

### Desktop VM: Ubuntu desktop
**Setting up ip address:**

![settingup ip in desk](https://github.com/user-attachments/assets/d6940e7c-b268-4a3c-8a9b-3dfacf4b3d33)

#### IP address of the adapter:
After setting the IP, verify the assigned IP address using the ip a command.

**Command: ip a**

![ipofall](https://github.com/user-attachments/assets/eb469b59-a26d-4af6-b20c-ae51769b0f0a)

#### Pinging to router:
To check if the Desktop VM can communicate with the router, ping the router's IP address <ins>(e.g., 10.0.2.15).<ins>

**Command: ping 10.0.2.15**

![ping router](https://github.com/user-attachments/assets/f00e9d37-060c-4b9e-b4fa-f396637d6388)

#### Pinging to Application Server:
Similarly, to check if the Desktop VM can communicate with Application server,ping the Application server (eg: 192.168.16.1).

**Command: ping 192.168.16.1**

<img width="319" alt="ping to application" src="https://github.com/user-attachments/assets/0e96fcec-4d21-4330-8ceb-dfc72c293d1f">

### Application VM: Bitnami Wordpress
#### Network configuration:
On the Application VM (Bitnami WordPress), configure the network settings by editing the /etc/network/interfaces file:

**Command: sudo nano /etc/network/interfaces**

![netconf](https://github.com/user-attachments/assets/66c9d92a-13d3-48da-aef3-aa798ad7b8ab)

#### IP address of all adapters:
Similar to the router and desktop VMs, check the IP address of all adapters on the Application VM using:

**Command: ip a**

![ipall](https://github.com/user-attachments/assets/66f12032-6a45-4617-acae-16dd5f73f415)

#### Pinging router:
Test if the Application VM can communicate with the router by pinging the router’s IP address (e.g., 10.0.2.15):

**Command: ping 10.0.2.15**

![pr](https://github.com/user-attachments/assets/05cbdedd-2344-4e16-bf01-033649afe203)

#### Pinging Desktop VM:
Finally, test communication from the Application VM to the Desktop VM (e.g., 192.168.116.1):

**Command: ping 192.168.116.1**

![pdesk](https://github.com/user-attachments/assets/9b4bc3e6-206d-48fe-82ee-1751a97aeeab)

#### Conclusion:
In this project, I successfully set up and configured a private virtual network that included a router running Ubuntu Server, a Desktop VM with Ubuntu Desktop, and an Application VM running Bitnami WordPress. The main goal was to create a secure, isolated network environment where I could apply networking concepts like IP addressing, subnetting, and interface configuration without any risk to live systems.

The setup involved adjusting network settings on each VM, assigning static IP addresses, and testing the communication between the devices. By performing ping tests, I confirmed that all VMs could successfully connect to each other and the router, as planned.

This project helped me get hands-on experience with the fundamentals of networking and highlighted the importance of getting the configurations right to ensure a working network. It also gave me a clearer understanding of the setup process and how to troubleshoot connectivity issues along the way.

Looking ahead, I could add more features to the network, like a firewall or DHCP server, to make it even more complex and functional. But overall, this project met all the goals, and I feel more confident in my understanding of networking fundamentals for future projects.




