
<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups (https://www.youtube.com/watch?v=Mu_2UnOdVHM)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

Step 1: Set up Azure Virtual Machines and establish network connectivity.

Step 2: Configure Network Security Groups (NSGs) to manage inbound and outbound traffic.

Step 3: Use Wireshark to capture and analyze traffic between VMs.


<h2>Actions and Observations</h2>

<p>

![image](https://github.com/user-attachments/assets/71d1db7f-f1a8-412a-a741-bb3ff055a81b)

![image](https://github.com/user-attachments/assets/a0024ad1-6b8e-4a1b-be28-3e357f61dfc5)

![image](https://github.com/user-attachments/assets/e9bae32e-c46e-4093-a8d2-4ea31f9293ee)

![image](https://github.com/user-attachments/assets/14cdaff6-ddf9-47df-9480-50a348d96bbf)

</p>
<p>
 In Azure Portal:

 1. Go to Virtual Machines.

 2. Click "+ Create" → "Azure Virtual Machine".

3. Select the RG-Windows resource group.

4. Enter a VM Name (e.g., Win10-VM).

5. Choose the same Region as the resource group.

6. Select Windows 10 as the image.

7. Choose a VM size (e.g., Standard B2s).

8. Set up Administrator credentials (username/password).

9. Under Networking:
   - Create a new Virtual Network (VNet) (e.g., MyVNet).
   - Let Azure create a new Subnet.

10. Click "Review + Create" → "Create".

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/941d60ff-d6ff-4b84-9e3d-1ec0240362a8)

![image](https://github.com/user-attachments/assets/e835bb75-67c8-44c8-b81e-140c192f6775)

</p>
<p>
 In Azure Portal:

 1. Go to Virtual Machines → "+ Create" → "Azure Virtual Machine".

2. Select the RG-Linux resource group.

3. Enter a VM Name (e.g., Linux-VM).

4. Choose the same Region.

5. Select Ubuntu (latest LTS) as the image.

6. Choose a VM size.

7. Configure authentication:
   - Use SSH key or password.

8. Under Networking:
   - Select MyVNet (the virtual network created earlier).
   - Choose the same Subnet.

9. Click "Review + Create" → "Create".

</p>

<br />

<p>

![image](https://github.com/user-attachments/assets/e007d4ff-8d92-44c2-aa05-73e828aaf0c2)

</p>


<p>
 In this step, we configure the network settings for our Azure Virtual Machines (VMs). We use Wireshark to capture the network traffic between the VMs to analyze the communication. As traffic flows between the Windows 10 and Ubuntu Server VMs, we can see various protocols in action, such as DNS, SSH, RDP, HTTP/S, and ICMP. This is a key part of monitoring network activity and understanding how different types of traffic interact within a virtualized environment.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/bb3cea8d-a826-4896-bbdc-38fdaa9b9ae5)

</p>
<p>
Network Security Group (NSG) rules can block or allow specific types of traffic between the VMs. For example, if we apply a rule that blocks ICMP traffic on DC-1, Client-1 will no longer be able to access any web services on DC-1. In Wireshark, this will be indicated as "Destination Unreachable" messages for ICMP requests.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/d9339366-c4bb-42da-a47e-5b455e6d64e7)


</p>
<p>
Wireshark helps in monitoring and analyzing the actual traffic between VMs in real-time.
</p>
<br />

<p>
