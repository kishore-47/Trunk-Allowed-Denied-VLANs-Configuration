Trunk Allowed/Denied VLANs – Cisco Packet Tracer

This project demonstrates the design and configuration of a Trunk with Allowed/Denied VLANs in Cisco Packet Tracer, showcasing how to control VLAN traffic between switches.

📘 Project Overview

This topology connects multiple PCs across VLANs (10, 20, 30) on two switches with a trunk link.
The trunk is configured to allow specific VLANs and deny others, ensuring controlled inter-switch communication.

Key Advantages:

Limits unnecessary broadcast traffic across trunk links.

Provides better security and segmentation.

Improves bandwidth utilization by filtering unwanted VLANs.

🖥️ Network Topology

Components Used:

Switches: 2 × Cisco 2960

PCs: 6 × PC-PT

Cables: Copper Straight-Through (PC–Switch), Copper Cross-Over (Switch–Switch)

IP Address Plan
Device	VLAN	IP Address	Subnet	Connected To
PC0	20	192.168.20.1	255.255.255.0	Switch0 Fa0/0
PC1	10	192.168.10.1	255.255.255.0	Switch0 Fa0/3
PC2	30	192.168.30.1	255.255.255.0	Switch0 Fa0/5
PC3	20	192.168.20.2	255.255.255.0	Switch1 Fa0/3
PC4	30	192.168.30.2	255.255.255.0	Switch1 Fa0/0
PC5	10	192.168.10.2	255.255.255.0	Switch1 Fa0/5
📂 Files
File Name	Description
trunk_vlan_allowed.pkt	Cisco Packet Tracer project file
README.md	Project documentation
topology_screenshot.png	Network diagram image
⚙️ Configuration Steps

1️⃣ Create VLANs

Switch(config)# vlan 10
Switch(config)# vlan 20
Switch(config)# vlan 30


2️⃣ Assign Access Ports

Switch(config)# interface fa0/3
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10


(Repeat for other PCs with correct VLANs.)

3️⃣ Configure Trunk

Switch(config)# interface fa0/2
Switch(config-if)# switchport mode trunk


4️⃣ Allow/Deny VLANs on Trunk

Switch(config-if)# switchport trunk allowed vlan 10,30
! (This allows only VLAN 10 and 30, VLAN 20 is denied)


5️⃣ Verify

Switch# show interfaces fa0/2 switchport

🎯 Learning Objectives

Understand VLAN trunking.

Learn how to filter VLANs using allowed/denied lists.

Practice troubleshooting inter-switch VLAN communication.

🧠 Key Notes

Default trunk allows all VLANs.

Use allowed vlan command to control VLAN traffic.

Both ends of the trunk must match configuration.

💡 Author

Kishore Anand M
🎓 B.Tech IT | 🧠 Pre-final Year
🔧 Aspiring Network Engineer | 💡 AI & No-Code Tools Explorer

🛡️ VLAN control ensures secure and efficient network communication.
