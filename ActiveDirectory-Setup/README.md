Step-by-Step Lab Guide
1. Environment Preparation

    Install VMware Workstation Player.

        Refer to: install_vmware_LI.jpg

    Download Windows Server 2019 Evaluation ISO.

        Refer to: download_isofile.jpg

2. VM Creation

    Create VM #1 for Windows Server 2019.

    Create VM #2 for the client system.

    Use "Installer disc image file (iso)" for the installation ([Screenshot-87.jpg]).

3. Server Configuration

    Install AD DS (Active Directory Domain Services) role ([Screenshot-97.jpg]).

    Promote the server to a Domain Controller, e.g., nothingtofear.local.

    Configure Server Manager and AD DS ([Screenshot-88.jpg], [Screenshot-90.jpg], [Screenshot-96.jpg], [Screenshot-95.jpg]).

4. User Creation

    In Active Directory Users and Computers, create a user (helpdesk ntf) ([Screenshot-93.jpg], [Screenshot-94.jpg]).

5. Joining Client VM to Domain

    On the client VM, open System Properties and attempt to join the domain (e.g., nothingtofear.local). ([Screenshot-91.jpg], [Screenshot-99.jpg])

    Problem: Direct entry of domain fails due to network/DNS issues ([Screenshot-99.jpg]).

Troubleshooting Step:

    Check the network adapter properties ([Screenshot-89.jpg]).

    Set the DNS server manually to point to the Domain Controller’s IP ([Screenshot-98.jpg], [Screenshot-92.jpg]).

    After correct DNS configuration, retry domain join ([Screenshot-91.jpg]). Now "helpdesk ntf" can log in successfully ([Screenshot-92.jpg]).

6. Final Verification

    Log in to client VM as the AD user helpdesk ntf ([Screenshot-92.jpg]).

    Computer shows as domain-joined in AD ([Screenshot-91.jpg]).

Problem Faced and Solution

Issue:
Directly entering the domain name during client join fails with an "AD DC could not be contacted" error.

Solution:
Manually set the preferred DNS server on the client VM's Ethernet adapter to the Domain Controller’s static IP address. This allows the client to resolve and contact the domain controller during the join process.
Screenshots

All referenced screenshots are included in the Screenshots folder. Each image illustrates a key configuration step or troubleshooting action.
Key Learning Outcomes

    AD setup and domain controller installation in a VM.

    Network configuration and DNS troubleshooting for domain joining.

    Manual user creation and successful domain logon from the client.

    Understanding network dependencies for AD environments.

Credits

Project by Rajnish kumar.
Lab practiced and documented for learning Active Directory, Windows Server, VMware Workstation, and troubleshooting domain setups.
