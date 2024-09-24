<h1>Active Directory Home Lab</h1>



<h2>Description</h2>
Project consisted of: 
Successfully buiding and configuring Windows Active Directory using Virtualbox 
Installed and optimized Windows Server 2019 and Windows OS on VirtualBox
Established a domain, added a forest, and created an Organizational Unit
Implemented NAT and DHCP services to stimulate real-world network scenarios 


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 


<h2>Environments Used </h2>

- <b>Windows 11</b> 
- <b>Windows Server 2019</b> 

<h2>Program walk-through:</h2>

<p align="center">
Make sure the Windows OS is on a bridged network (at first I had it on an internal network but the two VMs weren't able to communicate). <br/>

![Screenshot (14)](https://github.com/user-attachments/assets/29e5ed73-6bc9-459d-ad20-34a2268ff0ef)

<p align="center">
 The Domain Controller has one adapter connect to the local network and the other is conneced to an internal network, which is used for connecting to the Windows VM.

![Screenshot (16)](https://github.com/user-attachments/assets/79d9fb5a-5b9b-4f01-b99c-b3b4012b89f7)

<p align="center">
Go to adapter settings and the properties of the internal network. Give it an IP address and DNS server address.

![VirtualBox_DC_19_09_2024_14_54_52](https://github.com/user-attachments/assets/66dff9da-7706-4d5c-bc80-fd8bf3cf86d0)

<p align="center">
Within server manager, add roles/features which includes DHCP Server, Active Directory Domain Services, and Remote Access.

![VirtualBox_DC_19_09_2024_14_58_12](https://github.com/user-attachments/assets/80bd492b-59e8-4c9c-a030-f7d0f04470c9)

<p align="center">
Promote the server to domain controller & create a new forest under mydomain.com.

![Screenshot (6)](https://github.com/user-attachments/assets/4208ee2a-41a9-44e8-982f-1d7307483860)

![Screenshot (7)](https://github.com/user-attachments/assets/6c806387-0b0a-45a1-85bd-6449a77d9747)

<p align="center">
Configure Remote Access so that it's connected to the host network aka NAT.

![Screenshot (9)](https://github.com/user-attachments/assets/34f35e8c-8d30-4cad-8fe0-9d8c2849dd9f)

![Screenshot (10)](https://github.com/user-attachments/assets/b448a43a-5d81-48a0-be2b-cf3fc4a2b5ec)

<p align="center">
Now when logging in to domain controller, it'll say mydomain/admin.

![VirtualBox_DC_19_09_2024_15_03_37](https://github.com/user-attachments/assets/9b0e3e68-8155-44b6-90d0-8841cf24ccdc)

<p align="center">
Set up DHCP and create a new scope.

![VirtualBox_DC_19_09_2024_15_08_27](https://github.com/user-attachments/assets/05a0cb70-f007-4a58-be2a-b034fca73f01)

![VirtualBox_DC_19_09_2024_15_09_19](https://github.com/user-attachments/assets/2dfa50d8-5bad-4275-96e2-973529fcc8f3)

<p align="center">
Make sure the domain is authorized and refresh.

![VirtualBox_DC_19_09_2024_15_11_08](https://github.com/user-attachments/assets/e32bcef9-0cc8-4ec9-b989-e721149ccd48)

<p align="center">
Create a new user.

![VirtualBox_DC_19_09_2024_15_12_32](https://github.com/user-attachments/assets/403a84d2-cc10-4d18-9ccb-e2d876a2ad91)

<p align="center">
You should be able to log on to this new user account from the Windows OS.

![VirtualBox_window 10_24_09_2024_00_06_17](https://github.com/user-attachments/assets/006545a1-cdcf-451e-98f8-ba82a3817a34)

<p align="center">
In my case I manually entered the IP address on the Windows OS to ensure connection between the two VMs.

![VirtualBox_window 10_19_09_2024_15_20_06](https://github.com/user-attachments/assets/ba351142-0d85-446e-8248-de4d9efcb0c9)

<p align="center">
I pinged both VMs from the other to ensure everything was working. 

![VirtualBox_window 10_24_09_2024_00_08_40](https://github.com/user-attachments/assets/549cee66-0e47-412e-9633-3c8dc9f10581)

![VirtualBox_window 10_23_09_2024_23_59_43](https://github.com/user-attachments/assets/ab74a4d7-8090-4ab4-af6e-756cd9f84504)
