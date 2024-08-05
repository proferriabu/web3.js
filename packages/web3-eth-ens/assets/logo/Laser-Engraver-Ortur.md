Hi received Ortur Master V2 2 days ago Friday and it worked great, left it alone for one day, switched on today Sunday, no response, no homing, no fire, no move, says ready, and busy when burning but nothing except fan on laser module otherwise dead, pls help
thx
Howard
 
got it! the power adapter green light was on so it looked live, but socket was not live - so the power adapter light gets power from the laptop usb? eh? very confusing
it seems the issue is me!
Howard
 
**Download File ►►► [https://passrogmisslo.blogspot.com/?file=2A0QfQ](https://passrogmisslo.blogspot.com/?file=2A0QfQ)**


 
I explain
The ortur motherboard recieves 3v from 2 sources
USB (From your computer)
And also from power supply after a step down conversion.
If the PSU fails, the controller side of the board recieves enough power via USB to power up, and run the fan at lowww speed, but not enough power is present to run the laser and stepeers
 
Soft limits = Machine knows that if you try to send a GCode coordenate thats outside the Grbl settings max travle area, it will throw an error and not start work
Hard limits = Has to do with limit switches
 
My objective is having the laser cutter working on my balcony, outside (for fumes), and controlling it remotely, from my Studio via wifi.
Normally the ORTUR cutter connects via USB to my Macbook with LightBurn.
 
So I don't know anything about this plugin specifically but remembered running across it during one of my random github searches for OctoPrint. If I understand correctly, it's a plugin that will completely take over the OctoPrint UI and is geared toward laser cutters.
 
You might make a query in the Lightburn forum as well. There are a number of people who connect to their lasers via the network. In general, WiFi is bad for latency/jitter reasons. I do computerized Christmas lighting and people who try WiFi notoriously run into lag/busy problems. So if you want to use the laser control part of lightburn (start, frame, etc), you may have to leverage something like Octoprint that provides a smarter intermediary. I have generated gcode for Marlin using Lightburn and uploaded that to an SD card via one of the wifi SD emulators. That works well.

I run 2 3d printers and one laser engraver off of one Raspberry Pi 4. Octoprint\_deploy sets up multiple instances and saves the cameras and printers to each individual instance. Like octoprint.local/example\_of\_instance\_name\_one/
 
Bash script for rapid deployment of multiple octoprint instance on a single machine - GitHub - paukstelis/octoprint\_deploy: Bash script for rapid deployment of multiple octoprint instance on a sing...
 
Better Grbl Support Plugin for Octoprint based (loosely) on the original Grbl Support plugin developed by mic159 - GitHub - synman/Octoprint-Bettergrblsupport: Better Grbl Support Plugin for Octopr...
 
I do not have any other Ortur laser engravers and it looks like the updates include a drag chain, metal has been substituted for acrylic feet, grounding wires, emergency stop, flame detector. 24V instead of 12V, and a better Focus adjuster.
 
Building the machine was relatively easy. The printed instructions were small but I was able to work my way through them. The most difficult time I had was installing the timing belts. It took about an hour to fully build. I then installed the LM2Pro on a piece of scrap plywood.
 
I did run into one firmware issue but I was able to work around it. I really dislike sending G-code from a Windows machine so I started sending it via cncjs. cncjs would error out on some burns. After some troubleshooting and observations, I believe the Ortur board is sending something in its serial communications that cncjs is not interpreting properly. If I directly restart the connection between cncjs and the LM2Pro it works fine with the exception that the machine position is not updated nor the buffer window showing the status. If I reset the connection and start a burn I get updated positioning but the planner buffer always shows 0 and the receive buffer slowly fills up and errors out. I suspect that since the planner buffer is always showing 0 that cncjs keeps sending G-code until there is an overflow. I reported this to Ortur through its website and I am optimistic Ortur will provide an update to resolve this. I assume that this is super simple to fix. I was thinking about breaking out my logic analyzer but taking the easy route for now. The simple workaround is to always close and reopen the connection between each burn.
 
There has already been an update to firmware that I was hoping to fix the issue above but it did not. Upgrading firmware turned out to be really easy. Press and hold the power button for 5 seconds then while holding the power button tap the reset button. The board will show up as a drive on your machine. Drag and drop the firmware file to the root folder and after a bit of time the machine reboots. Then check your console to make sure it reflects the new firmware version. Directions were very clear and easy to follow.
 
If you have a laser engraver, I am convinced Lightburn is the way to go. It is not free but is extremely powerful. The $40 cost is well worth it in my opinion. There is a 30-day unrestricted trial. The feature that really got me excited is its webcam integration. If you notice in the picture above I installed a fixed webcam. It is a Logitech C930. All cameras have lens distortion and the software guides you through a calibration process to remove this (see video guide). What this allows you to do is place an object in your burn area and perfectly line up whatever you are engraving.
 
This was nearly my first test. You can see in the black and white image that I had purposefully put my test piece on an angle. Then the other image shows the outcome. Please overlook the lightness of this burn.
 
My first impressions are great. Especially, after spending so much time trying (and mostly failing) with the previous laser setup doing the Norton tile method. I found the LM2Pro easy to assemble. I will follow up with a long-term impression post. I ordered and received a small pump to test out air assist with cutting. I also went to a dollar tree and bought a bunch of test items to try different techniques. Canvases, Plates, Glass items, cheap stainless steel knife, and some wooden craft items from a dollar general. I also have some ideas for some bigger projects with the tile method. I also want to try incorporating the LM2Pro with CNC work. So many possibilities.
 
One of the claims on the review documentation was that beam was smaller than usual and more round. I will see how I can test this and take in your suggestion. Documentation is claiming the old laser module was .23x.23 and the new is .08x.15. I have been running & .1 so I do think it is improved. Tiles really made this apparent. With the previous laser if I had any overlap it would burn the previous line off the tile.
 
It takes some configuration and tweaking in the laser engraving software (LightBurn or LaserGRBL), but once that setup is done, the rotary tool enables users to engrave cylindrical objects like mugs, glasses, tumblers, baseball bats, etc.
 
I enjoy when my interests overlap. I especially enjoy when they happen as blog topics. For example, 3D-printing parts for my quadcopters, using home automation to monitor my 3D printing, and most recently 3D-printing parts to use with my laser engraver as part of this blog!
 
Having an Ortur YRR 2.0 enables you to engrave an entirely different shape of material. It accomplishes this fairly inexpensively, without a tremendous amount of effort to assemble or effort dialing it in. I do not have a tremendous amount of experience with laser engraving, but I had it working fairly quickly.
 
To give you the best possible experience, this site uses cookies. Using the site means your agree to our use of cookies. We have published a new cookies policy, which you should need to find out more about the cookies we use. View Cookies Policy.
 
Super High Power Laser Engraver - ORTUR's newest real 10W optical power laser engraver. The laser output power soars up with the latest generation of two 5.5W laser coupling technology, is able to cut off 10mm pine board with only one pass, and even cut the 30mm thick black acrylics without any issue.
 
Compared to other 10W laser cutters & engravers, the Ortur Laser Master 3 has a superior laser head design resulting in a smaller focal spot of 0.05 x 0.1mm which allows you to capture delicate details in your projects.
 
The Ortur Laser Master 3 can be connected via USB to a computer for use with softwares such as LightBurn and LaserGRBL or it can be connected to a mobile phone or tablet via Wi-Fi for use with the Laser Explorer app!
 
Not only can you engrave on flat objects, you can also engrave on cylindrical! A YRR switch can be found at the top of the machine which once switched allows you to connect a rotary attachment and engrave on cylindrical objects.
 
Once I updated the firmware and installed the Laser Explorer app on my phone, connecting to WiFi was relatively easy following the manual and I was able to connect and engrave some test pictures from the app including a duck and ice cream cone. The Laser Explorer app was actually the easiest interface to use compared to the PC based LaserGRBL and LightBurn. Being a total newbie to laser engraving the app gave me a good preview of the most common settings and functions to control the laser and it allowed me to easily print pictures I had taken on my phone.
 
I found an additional helpful manual for the Laser Explorer app after the fact that was not included in the files on the SD card. Unlike 3D printers, you should never leave a laser operating unattended due to the fire hazard but the Ortur Laser Master 3 laser engraver has quite a few built-in safety features including a keyed safety lock to prevent un