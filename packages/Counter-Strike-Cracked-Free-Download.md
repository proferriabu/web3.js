
 
I'm using an Intel Arc A750 LE and after upgrading from the 4887 WHQL driver to 4952, 4953, and 4972, I've noticed that there are occasional texture flickering issues in Counter-Strike 2 (CS2) using DX11. I've used DDU in safe mode for all upgrades and I've cleared the DirectX Shader Cache. The GPU is not overclocked.
 
**Download File ⚹ [https://passrogmisslo.blogspot.com/?file=2A0QuN](https://passrogmisslo.blogspot.com/?file=2A0QuN)**


 
It seems to happen most at round starts, showing of scoreboard, and when bringing up the chat wheel. It looks like a bit of (mostly) white static noise across the display. It goes away within a second or so, but it is distracting. It probably happens 5-10 times during a 10 minute gaming session.
 
I've given the new **31.0.101.5074** driver some more thorough testing with MSAA enabled in Counter-Strike 2 and my conclusion is that the issue has been fully addressed. The issue appears to have been introduced as a regression in driver 4900 or 4952.
 
Thank you for providing us with all the necessary information. We understand that it may take some time to capture the video demonstrating the issue you are facing. We would like to assure you that we are willing to wait until you share the video with us. Also, please let us know if you encounter any difficulties while recording the video.
 
I've tried to capture a video of the issue with the Intel Arc Control software, but even though the flickering is visible on the monitor, it isn't captured in the output even with the highest capturing resolution, frame rate, and bitrate. So, instead I captured it with my phone camera (most visible around the 4-5s mark):
 
This is driver 4972 on an Arc A750 LE using DX11 (DDU'ed, etc). The issue seems to be affected by the anti-aliasing settings. The video above is with MSAA x8, but I've seen the issue with MSAA x2 too. If I use CMAA2 instead, the problem appears to go away. Attached is the SSU report from the system after updating to driver 4972 and reproducing the issue. The issues seems to be a regression since driver 4887 (WHQL) does not exhibit the same behavior.

I've tried with Vulkan too (specifying -vulkan as a launch option), but there is a whole new level of texture glitches on Vulkan both with MSAA x8 and CMAA2. Others have reported the same thing, so I does not appear that using Vulkan is a good choice for Counter-Strike 2 just yet.
 
Thank you for taking the time to record the video and capture an image that shows the graphical error. We appreciate your efforts in providing us with the necessary information to understand the issue you have described. We will be conducting a thorough internal review of this issue reviewing the information you shared. We will keep you updated as soon as we have more details.
 
Thank you very much for providing us with the information. We appreciate your effort in testing the game with different settings. The more details we have, the better we can investigate this matter. We want to inform you that we are still investigating this issue, and although we don't have an update yet, rest assured that we are working on it.
 
We would like to inform you that we are still investigating this issue internally. Although there isn't a current update on this, we are actively addressing the issue and will do so as soon as we can.
 
Do let me know if you find the reported issue reproducible or not. If the engineering team has a hard time reproducing the issue, I'd be happy to help out any way I can. Reproducing an issue is usually the most significant part of solving an issue.
 
Are there any updates on the reproducibility of the reported issue? I see a number of reports of poor MSAA performance on the Community Issue Tracker, but is unclear if those are related to the anti-aliasing induced flickering I reported back in November.
 
Thank you for getting back to us on your thread. We want to let you know that we're still investigating the problem internally, but we don't have any updates to share at this time. We understand that other users have reported similar issues with MSAA, but we need to look at each issue to determine the root cause. It's possible that even if two users are experiencing the same symptom, but different applications, the underlying cause may be different. That's why we need to investigate and confirm the root cause of each issue before we can implement a fix.
 
I've done a quick round of testing on the new **31.0.101.5074** driver and it appears as if the problem has been addressed, not just on MSAA x4 as noted in the release notes, but also on MSAA x2 and x8. I will start using MSAA anti-aliasing in Counter-Strike 2 from now on and make notes of any issues I discover. Give me a few days and I should be able to confirm if the issue is really gone.
 
We appreciate your efforts in testing the new driver version. We are glad to know that it seems that the issue has been addressed, but you would like to play the game using g MSAA anti-aliasing in Counter-Strike 2 taking note of any problems you may discover. We will wait for you to test the game. Please do not hesitate to let us know if your original issue persists. If you encounter a different problem, we recommend that you submit a new thread. Reporting one issue per thread will help us keep the topics organized. We will wait for your response after testing the game.
 
We have received your feedback regarding the MSAA problem in Counter-Strike 2 and we are pleased to inform you that the issue has been resolved. As a result, we will be closing this thread. If you require additional assistance, please create a new question, as this thread will no longer be monitored.
 
Intel does not verify all solutions, including but not limited to any file transfers that may appear in this community. Accordingly, Intel disclaims all express and implied warranties, including without limitation, the implied warranties of merchantability, fitness for a particular purpose, and non-infringement, as well as any warranty arising from course of performance, course of dealing, or usage in trade.
 
So it goes. Counter-Strike has always been viciously cruel to newcomers. As a pioneer of the one-life-per-round multiplayer shooter, the game has long been about five-on-five multiplayer matches that see combatants slowly whittled down as the round draws on. Casual game modes up the player count substantially, but that feeling of attrition as players get wiped out, littering the map with their corpses, remains.
 
The two teams, terrorists and counter-terrorists, fight over a bombsite or a few kidnapped hostages: opposing objectives that see one or the other team taking a defensive angle while the other tries to bust in and complete their objective. In most competitive settings, these games will all involve the bomb defusal mode, which revolves around counter-terrorists trying to hold a bomb site while terrorists try to attack it, planting the bomb and holding it for 40 seconds before it explodes, killing everyone nearby.
 
Jake Tucker is the editor in chief of TechRadar Gaming and has worked at sites like NME, MCV, Trusted Reviews and many more. He collects vinyl, likes first-person shooters and turn-based tactics titles, but hates writing bios. Jake currently lives in London, and is bouncing around the city trying to eat at all of the nice restaurants. "}), " -0-10/js/authorBio.js"); } else  console.error('%c FTE ','background: #9306F9; color: #ffffff','no lazy slice hydration function available'); Jake TuckerSocial Links NavigationEditor in chief, TechRadar GamingJake Tucker is the editor in chief of TechRadar Gaming and has worked at sites like NME, MCV, Trusted Reviews and many more. He collects vinyl, likes first-person shooters and turn-based tactics titles, but hates writing bios. Jake currently lives in London, and is bouncing around the city trying to eat at all of the nice restaurants.
 
***Counter-Strike*** (also marketed as ***Half-Life: Counter-Strike***) is a multiplayer first-person shooter initially created by Minh Le and Jess Cliffe as a mod for *Half-Life*. By the fifth beta, Valve Software started actively participating in the development and ultimately bought the rights to the game and offered the original developers jobs at the company which both of them accepted.
 
After about a year in Beta stages, the first full release of the mod was published on November 9, 2000 and the game was also available at retailers in North America shortly thereafter, on November 14, 2000.
 
The fast-paced and team-oriented gameplay of *Counter-Strike* has stayed relatively the same throughout the years. In it, two teams, the Counter-Terrorists and the Terrorists, fight to complete an objective or eliminate the opposing team. Although basic, it is considered one of the most revolutionary online games of all time. The original Counter-Strike came exclusively with multiplayer, without computer-controlled players. Over time, however, several server-side modifications have added bots for in-game use and bots were officially introduced in its later successors, *Counter-Strike (Xbox)* and *Counter-Strike: Condition Zero*.
 
*Counter-Strike* has been praised worldwide for its highly competitive multiplayer. The decision to make the game multiplayer only roots back to its mod origins. Doing a single-player game would have entailed much more work as new models and AI code would have been needed for enemies as opposed to a multiplayer game which requires considerably less work.[1]
 
There are three official scenarios in *Counter-Strike*: Assassination, hostage rescue and bomb defusal. A fourth scenario, known as escape, existed during the *Counter-Strike Beta*. The scenario itself is still playable, but all of the official maps were removed prior to the game's release.
 
In this scenario hostages are being held by the Terrorists. Official maps feature between 3 and 5 hostage