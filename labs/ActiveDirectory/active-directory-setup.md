# Lab: Setting up Active Directory Domain Services

# Lab Environment
- Host OS: Windows 11
- VM Platform: VirtualBox
- Guest OS: Windows Server 2022
- Network: Bridged Adaptor

# Objective
Install and configure Active Directory Domain Services (AD DS) to create a domain controller for a test network.

# Steps Taken
1. Downloaded the Windows Server 2022 ISO from Microsoft Evaluation Center
2. Created a new VM in VirtualBox and installed the Server Core edition
3. Configured hostname and static IP
4. Installed the AD DS role with:
   ```powershell
   Install-WindowsFeature AD-Domain-Services

5. Promoted the server to a domain controller:
   ```powershell
   Install-ADDSForest -DomainName "mico.local"

6. Rebooted and verified AD installation with:
   ```powershell
   Get-WindowsFeature AD-Domain-Services

# Issues Faced
- "sconfig" was hanging, had to resolve it by temporaryily disabling the network adapters
- Initial reboot failed until memory was increased from 2GB --> 4 GB

# Skills Practiced 
- Windows Server installation
- PowerShell usage in Server Core
- Domain creation and AD DS role configuration
- Troubleshooting issues with network and resource allocation
