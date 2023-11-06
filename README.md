# SOC-Home-Lab-Lima-Charlie
Working in VM Workstation Pro, I set up a Windows VM and a Linux VM. Then, using the Linux VM, created malware and deployed it on the Windows machine.

First, I set up the Linux VM and created the malware. Next, I set up the Windows Vms. Next, I disabled Windows Defender on the Windows system and downloaded a payload created with Sliver C2 from the Linux machine. Lastly, using LimaCharlie EDR, analyzed logs on the Windows machine and wrote custom detection rules to generate alerts anytime this program was executed.
 ### [YouTube Links]
 [Part 1] (https://youtu.be/3O43XAf0ml8)<br /> 
 [Part 2] (https://youtu.be/Mx7g_4DZAtk)<br />
 [Part 3] (https://youtu.be/XxLBAcZhqTQ)<br />
 [Part 4] (https://youtu.be/uvr8S8Z3EeI)<br />
 [Part 5] (https://youtu.be/fVIprhn_hcw)<br />


<h2>Set Up the VMs</h2>
<b>
VMware: Download and install a free trial of VMware Workstation.
 
Windows VM: Download and deploy a free Windows VM directly from Microsoft. Get the “VMWare” version of the workstation. Once downloaded, unzip the VM and double-click the WinDev####Eval.ovf file to import the VM into VMware, but do not start it up yet.<br />
 Once imported, if you have 16GB or less of RAM on your system, you may want to modify the amount of RAM allocated to the Windows system — it has 8GB by default but can run with 4GB. If the VMs run slow, it may be due to not enough free RAM on your host.

Linux: Download and install Ubuntu into a new VM. Download the Ubuntu Server 22.04.1 installer ISO.<br />
 *NOTE: I am specifying the SERVER version of Ubuntu because it comes preinstalled with the necessary packages. If you choose the Desktop flavor, you will have issues, and you are wasting unnecessary resources.*
Once downloaded, create a new VM in Workstation with the following specs

   Use the downloaded ISO as the installer image

14GB Disk size

Customize Hardware

2 CPU cores

2GB RAM

During OS install, leave defaults unless otherwise specified

Use Tab to navigate, Space to check boxes, Enter to confirm

“Installer update available”

“Continue without updating”
</b>

<h2>Set Up the VMs</h2>
<b>
VMware: Download and install a free trial of VMware Workstation.
 
Windows VM: Download and deploy a free Windows VM directly from Microsoft. Get the “VMWare” version of the workstation. Once downloaded, unzip the VM and double-click the WinDev####Eval.ovf file to import the VM into VMware, but do not start it up yet.<br />
 Once imported, if you have 16GB or less of RAM on your system, you may want to modify the amount of RAM allocated to the Windows system — it has 8GB by default but can run with 4GB. If the VMs run slow, it may be due to not enough free RAM on your host.

Linux: Download and install Ubuntu into a new VM. Download the Ubuntu Server 22.04.1 installer ISO.<br />
 *NOTE: I am specifying the SERVER version of Ubuntu because it comes preinstalled with the necessary packages. If you choose the Desktop flavor, you will have issues, and you are wasting unnecessary resources.*
Once downloaded, create a new VM in Workstation with the following specs

   Use the downloaded ISO as the installer image

14GB Disk size

Customize Hardware

2 CPU cores

2GB RAM

During OS install, leave defaults unless otherwise specified

Use Tab to navigate, Space to check boxes, Enter to confirm

“Installer update available”

“Continue without updating”
</b>
<br />
<br />
The script is used in this demo where I set up Azure Sentinel (SIEM) and connect it to a live virtual machine acting as a honey pot.
We will observe live attacks (RDP Brute Force) from all around the world. I will use a custom PowerShell script to
look up the attackers' Geolocation information and plot it on an Azure Sentinel Map!
<br />
<br />


<h2>Languages Used</h2>

- <b>PowerShell:</b> Extract RDP failed logon logs from Windows Event Viewer 

<h2>Utilities Used</h2>
