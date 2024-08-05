For the last 10 years I used various mail providers: mail.ru, Google Mail, Outlook (previously Live Mail), Office 365. They all have good and bad parts, but recently I made my decision to move from Google Mail/Outlook to FastMail
 
At first I really thought about setting up my own email server. I used for some time my own home server with OS X Server, also I wanted to try something in the cloud with one of the Open Source or paid solutions.
 
**DOWNLOAD ✵ [https://passrogmisslo.blogspot.com/?file=2A0PKv](https://passrogmisslo.blogspot.com/?file=2A0PKv)**


 
I tried to setup various solutions on VPS in the cloud. One of the solutions was open source iRedMail with RoundCube, the other solutions was Open-Xchange (this one is paid solution). Both of them are ok, but I was not satisfied. First of all - having own mail server takes a lot of your time (configuration, updates, spam lists). Also at minimum you will need to pay $10/month for VPS hosting.
 
One thing was not really obvious for me, that in main menu there are two links for settings: Settings and Advanced. I automatically for 5 minutes kept clicking on Settings link and trying to find Advanced settings somewhere in Settings window before I realized that I need to use separate menu item Advanced
 
Subdomains is the first awesome feature which you are going to get from FastMail. For example, if you want to use email me@example.com and also you want to have separate emails with specific identifiers for various services like me+dropbox@example.com or me+mybank@example.com - you will meet a lot of services which do not allow you to use + in email alias. FastMail has a solution for this, it can automatically swaps mybank@me.example.com to me+mybank@example.com and sends emails to me@example.com. You can specify this per domain.
 
The other part, which you need to specify on this page is the list of aliases you want to use for each domain. For example if you have domain example.com and you want to use email me@example.com just add record me @ example.com target to example@fastmail.fm
 
Use FastMail name servers for domains. This means that FastMail will have whole ownership over your domain. It automatically setups MX records and also gives you an option to specify other DNS records if you need.

Give it some time to propagate all settings and after that you can try to send emails to your own email addresses. You can also use terminal command on OS X dig -t MX example.com to verify that MX records are set correctly.
 
With the FastMail account you also get 5Gb of storage (for $40/year) which you can use for Static WebSites or some picture galleries. But just be aware that your account has limits for the uploading/downloading files from your file storage. So if your website is very popular - FastMail storage is not a right place for hosting it.
 
If you will go to the Advanced -> Websites/Redirects - this is where you also can setup redirects, like in my case I have a redirect from outcoldman.ru to outcoldman.com (just a reminder that outcoldman.com is still hosted by Namecheap, so Namecheap knows where the real location of my website). These, for example, two records I have
 
If you decided to use FastMail name servers for some of your domains and you need to specify DNS records you can do it on Advanced -> Custom DNS records. As I said in my case I kept all real web sites with name servers where I bought it, so I did not need to setup it with FastMail.
 
After that just click Migrate button and wait. At the end of migration process you should get email on your FastMail account IMAP Migration report with the detailed information about migration process.
 
The next important part which will help you to forget about all other Email accounts on other services: setup FastMail to periodically fetch emails from other accounts using POP3. After that step you also can answer on emails using your old Email Accounts like Google Mail or Outlook directly from FastMail.
 
You can do it in two ways. Advanced way is to use Advanced -> Pop Links. The easiest one is to use Settings -> Accounts. I used the easiest way. Go to the bottom of the page Settings -> Accounts and just add all of your other Email accounts, like Google Mail, Outlook, your Internet Provider email and anything else you want to work with
 
When you register new trial account with FastMail it asks you to specify one of the old Email accounts. In my case it was my Google Mail account. You will probably find it in the list of the Accounts on Settings page. But FastMail on registration does not setup POP links for this account. And it does not allow you to specify this account second time on this page. The easiest way which I found is to just remove this account and add it back.
 
An interesting feature could be to offer also some alternatives (open source or self-hosted, or even commercial) : 
AnonAddy, SimpleLogin, etc.
And some other email provider, very secure like ProtonMail or Tutanota, or more classical one (like Infomaniak here in Europe).
 
I was wondering about Vaultwarden (the "new" name of Bitwarden), and this "not so perfect" move from you is encouraging me.
Please listen to your users, who don't only look for simple process but also for your longtime engagment for privacy.
 
We will continue to monitor the situation with Australia's laws and the potential impacts there and act accordingly should the outlook change. Another resource I'd point to is our recent podcast episode with Fastmail's CTO where we deep dive on this important topic:
 
We can absolutely consider supporting additional providers for this feature in the future. One of the reasons for choosing Fastmail for this initial rollout is that we want to help promote JMAP, the open source tech that powers this integration. You can read more about JMAP here:
 
I'm very excited to see the new collaboration with FastMail, and I've signed up for the free trial. However I do agree with @ericgui . It would be a very nice addition to have multiple options to choose from.
 
I think SimpleLogin offers a really nice service, similar to FastMail. It's open-source, offers a free plan and the premium plan is about the same price as FastMail. I think SimpleLogin would make an excellent addition to the current arsenal of 1Password collaborations because it's open-source, has PGP and offers features like custom alias, reverse alias, one-click unsubscribe, quarantine, email forwarding to your own address and (in my opinion) much better control of individual aliases. It's also based in France which, as @ericgui mentioned is more respectful of privacy than the USA for example.
 
A few weeks ago, I decided to migrate my mails from HEY to Fastmail. The reasons were not in any way related to the quality of HEY service, in fact I was a very happy HEY user, I liked the overall flow and design, all rather simple but fitting my needs well. I had even written a series of blog posts about the cool HEY technology earlier and, as a Rails developer, I was really happy about this blow of fresh air in the front-end dev area.
 
**Why Fastmail?** Frankly, there was no big particular reason for me. I saw it recommended often on Twitter, briefly compared its features to a few alternatives, and decided to go with it. After using HEY for a year, all other mail services just look somewhat similar to me.
 
Other stuff that is important to me is about the same: both services have good security measures, good mobile apps, nice key bindings and their interfaces are fast. And, finally, there is a way back if you change your mind (see below).
 
Now, back to rule #1: if some of the rules directs a message to one of the special folders but I want it to go to Inbox instead, I can create an exception like this. In particular, this rule stores my mail notifications from GitHub to the Inbox, as opposed to saving it to the Feed folder.
 
After the migration finishes, chances are that some of your mail got into your Inbox instead of the Feed or Paper Trail. This is a nice opportunity to **cultivate your filtering rules**.
 
New mails from unknown senders arrive to the **Screener** folder. This folder is normally empty and hidden so when you do see it, it means there is something waiting patiently for your attention. You basically have two options now:
 
Now that you have the future all set with this sender, you still need to move this first message to the proper folder or delete it. I really recommend learning the Fastmail keyboard shortcuts as they speed things up tremendously.
 
One of them is **message pinning**. You can pin any message to set it aside from the normal flow. To be able to find it again later, you can save a custom advanced search (called e.g. **Set Aside**) that will filter only pinned messages by searching for "is:pinned".
 
Also note that, unfortunately, **Fastmail does not keep your email address** and is OK with reselling it after you cancel your account so you may have to pay an extra year there to make sure you notify all your senders properly about your new / restored address.
 
Thank you for the thorough and very helpful overview. I implemented most of what you laid out here. I'm glad to see Fastmail is still around and I intend on subscribing. I was really hoping Hey was going to be a great option for me in the long run but after the two years of trying it, I really wasn't as impressed with it as much as I thought I was. I also think you're right that the leadership has taken their opinionated stance too far in some regards.
 
I wish e-mail was not that cumbersome to self-host. There's maddy, but it lacks the GUI so it's not for everyone, though it's quite feature-packed (but still requires a good amount of knowledge to configure)
 
I'm not entirely sure why people would choose Hey in the first place. I don't think it offered any novel features, and from this post I can see that the only things y