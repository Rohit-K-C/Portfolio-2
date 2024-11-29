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

#### Command: sudo nano /etc/netplan/50-cloud-init.yaml

![network configuration-router](https://github.com/user-attachments/assets/9d8808ef-e121-4310-8415-cfbac0824fe1)

#### IP address of all adapters:
After configuring the network settings, you can verify the IP addresses assigned to each network interface on the router by using the following command:

#### Command: ip a

This command will display all IP addresses associated with the router’s network interfaces.


![ip adapter](https://github.com/user-attachments/assets/e4846848-05e3-409a-920e-c047e2fbadaf)

#### Pinging Desktop VM and Application VM:
#### Command: ping 192.168.16.1
![pinging both](https://github.com/user-attachments/assets/2faf1846-b4f4-4675-bda7-833817de2fd3)


### Desktop VM: Ubuntu desktop
#### Setting up ip address:
![image](https://github.com/user-attachments/assets/06f92815-2a8c-4125-90e9-f6b7843fce2a)

#### IP address of the adapter:
Command: ip a

![ipofall](https://github.com/user-attachments/assets/eb469b59-a26d-4af6-b20c-ae51769b0f0a)

#### Pinging to router:
Command: ping 10.0.2.15

![ping router](https://github.com/user-attachments/assets/f00e9d37-060c-4b9e-b4fa-f396637d6388)

#### Pinging to Application Server:
Command: ping 192.168.16.1

<img width="319" alt="ping to application" src="https://github.com/user-attachments/assets/0e96fcec-4d21-4330-8ceb-dfc72c293d1f">

### Application VM: Bitnami Wordpress
#### Network configuration:
Command: sudo nano /etc/network/interfaces

![netconf](https://github.com/user-attachments/assets/66c9d92a-13d3-48da-aef3-aa798ad7b8ab)

#### IP address of all adapters:
Command: ip a

![ipall](https://github.com/user-attachments/assets/66f12032-6a45-4617-acae-16dd5f73f415)

#### Pinging router:
Command: ping 10.0.2.15

![pr](https://github.com/user-attachments/assets/05cbdedd-2344-4e16-bf01-033649afe203)

#### Pinging Desktop VM:
Command: ping 192.168.116.1

![pdesk](https://github.com/user-attachments/assets/9b4bc3e6-206d-48fe-82ee-1751a97aeeab)






