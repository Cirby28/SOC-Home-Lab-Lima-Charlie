# SOC-Home-Lab-Lima-Charlie

<h1>Failed RDP to IP Geolocation Information</h1>


 ### [YouTube Links]
 [Part 1] (https://youtu.be/3O43XAf0ml8)<br /> 
 [Part 2] (https://youtu.be/Mx7g_4DZAtk)<br />
 [Part 3] (https://youtu.be/XxLBAcZhqTQ)<br />
 [Part 4] (https://youtu.be/uvr8S8Z3EeI)<br />
 [Part 5] (https://youtu.be/fVIprhn_hcw)<br />


<h2>Description</h2>
<b>The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third-party API to collect geographic information about the attackers' location.
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
