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

Use Tab to navigate, Space to check boxes, and Enter to confirm

“Installer update available”

“Continue without updating”

<b>Stop Here<b />
<p align="center">
<img src="https://i.imgur.com/SMNBm9m.png?3" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
<h2>Edit Network Connections</h2>
<p align="center">
<img src="https://i.imgur.com/6dOeZBe.png?1" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
<p align="center">
<img src="https://i.imgur.com/PPQFpcw.png?3" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
<p align="center">
<img src="https://i.imgur.com/dc0sRIG.png?1" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
<p align="center">
<img src="https://i.imgur.com/HmG1pOY.png?3" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
After this, continue to set up the VM with default settings. When asked to install OPENSSH server, we click "yes" and continue. Next, we move to the Windows VM.

<h2>Disable Defender on Windows VM</h2>
Power on the Windows VM.<br />
Next we are going to permanently disable Microsft Defender.<br />
Disable Tamper Protection<br />
Click the “Start” menu icon<br />
Click “Settings”<br />
Click “Privacy & security” on the left<br />
Click “Windows Security”<br />
Click “Virus & threat protection”<br />
Under “Virus & threat protection settings” click “Manage settings”<br />
Toggle OFF the “Tamper Protection” switch. When prompted, click “Yes”<br />
<p align="center">
<img src="https://i.imgur.com/T9zZuNB.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>
While you’re in there, toggle every other option OFF as well, even though we’re about to take care of it a couple of different ways.<br />
Close the windows we just opened.<br />

</b>
<h2>Install Sysmon</h2>
 <p align="center">
<img src="https://i.imgur.com/4383EhM.png?1" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

Check for Presence of Sysmon Event Logs
<p align="center">
<img src="" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Set Up Lima Charlie</h2>
 <p align="center">
<img src="https://i.imgur.com/SO3LnAC.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<p align="center">
<img src="https://i.imgur.com/N5YsXXR.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<p align="center">
<img src="https://i.imgur.com/ccWLMRT.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<p align="center">
<img src="https://i.imgur.com/rmn7p35.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Generate Sliver C2 Payload</h2>
<p align="center">
<img src="https://i.imgur.com/9NSX0PK.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Start Command and Control</h2>
<p align="center">
<img src="https://i.imgur.com/eUDDTVi.png?1" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Observe EDR Telemetry So Far</h2>
<p align="center">
<img src="https://i.imgur.com/gYXTLyc.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<p align="center">
<img src="https://i.imgur.com/Jl8B1IH.png?1" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Advaserial Proc Dump</h2>
<p align="center">
<img src="" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Proc Dump Detection</h2>
<p align="center">
<img src="https://i.imgur.com/Jl8B1IH.png?1" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Write a Custom Rule to Detect the Malware</h2>
<p align="center">
<img src="https://i.imgur.com/hbFTiCA.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<p align="center">
<img src="https://i.imgur.com/weggJdX.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>



<h2>Proc Dump Again and Notice New Telemetry in Lima Charlie</h2>
<p align="center">
<img src="https://i.imgur.com/ktxXSmr.png" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

</b>
<br />
<br />
With that the lab is done. We have created a malware, launched it, and also detected it. More can be done with this lab, such as using Velociraptor to create more aggresive detection rules that will better protect the computer. However, that is outside of the scope of the current lab.
<br />
