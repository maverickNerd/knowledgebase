For running tools required for pentesting, you need to setup your own linux.

There are many linux flavour available in market, like Ubuntu, RedHat, OpenSuse but Kali is one of the best for people in infosec as it
contains all the tools preinstalled which are required by any pentester.

It is always better to install Kali as a guest OS/virtual OS, on top of existing OS like windows, reason is, since kali OS is going to be the source of all attacks what you
are going to do against other target(other PCs/Websites), even if your own system got hacked by unethical people it will only effect the vmware OS only, not the original OS on top of which you are running your kali.

So, before installing Kali OS, you need to install hypervisor software, there are 2 well supported hypervisor available in market, VMWare and VirtualBox.

I personally like working with Vmware, so download and install Vmware from this link - https://www.vmware.com/products/workstation-player.html

Once Vmware got installed, download zip file of kali linux from this link - https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/

or if you applied for OSCP, you will get a download link of kali from OSCP in a mail. Only difference between these 2 kali version is that the OSCP kali linux contains some extra preinstalled tools which might be needed during OSCP.

Unzip above file using 7z software, you can download 7z from here, if you don't have it already: https://www.7-zip.org/download.html

Go to the extracted folder and open file having type as Vmware virtual machine configuration(Kali-Linux-2019.1-vm-amd64). Once it get opened it will show prompt like below:

Click on "I Copied It".

Once it boots, type Username: root and Passwords: toor

There might be chances that you need to change the network adapter settings.

VMware offers 3 options for virtual network connections: bridged, NAT, and host only. You should choose the bridged option, but below is the info on each:
- Bridged network: It connects the virtual machine directly to the local network using the same connection as the host system. As far as the local network is concerned, our virtual machine is just another node
on the network with its own IP address.
- NAT(Network Address Translation): It sets up a private network on the host machine. The private network translates outgoing traffic from the virtual machine to the local network. On the local network, traffic from
the virtual machine will appear to come from the host machine’s IP
address.
- Host-only network: It limits the virtual machine to a local private network on the host. The virtual machine will be able to communicate with other virtual machines in the host-only network as well as the host machine itself, but it will not be able to send or receive any traffic with the local network or the Internet.

Chose Bridge Network Connection:
'''
Go to player-> Machine -> Virtual Machine Settings -> Bridged option.
'''


To learn Linux : https://linuxjourney.com/
https://ryanstutorials.net/linuxtutorial/

if you want to learn kali linux:

you can skip wireless part from this video:
https://www.youtube.com/watch?v=0uvWRwLs5Zo
kali linux book: https://kali.training/downloads/Kali-Linux-Revealed-1st-edition.pdf



If you want to understand any command, you can put the command in below website to get help about it:
https://www.explainshell.com/
