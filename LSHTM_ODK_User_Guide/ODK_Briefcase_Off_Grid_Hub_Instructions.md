###**ODK Briefcase as an off-grid hub : Basic usage**

Background : In some situations it may be necessary to work entirely off-grid, for instance in places where there is no viable route to the internet or where internet services have been interrupted. In these situations it is preferable to continue to aggregate, backup and manage data in close to real time. One solution is to use ODK Briefcase, running on a laptop or mini-computer such as the Raspberry Pi, to gather the data from the various Android devices being used in the field. ODK Briefcase will automatically organise a project's files in a central data structure that can later be synced with a web-accessible ODK Aggregate server. 

In practical terms, the use of ODK Briefcase as an off-grid hub can make it possible to aggregate data in zero internet settings and all required functionality is built in to the software out of the box. Because it can run on a laptop, the person gathering the data is mobile enough to go to the field teams rather than requiring the field teams to come to them at a central facility. This has the potential to save resources and time.  

The rationale for this document is that we have been asked by multiple end-users to put together a simple practical guide on how to use ODK Briefcase to first pull data from multiple tablets, then to push up to an ODK aggregate server.

Note that the ODK Collect, Aggregate and Briefcase systems are able to resolve conflicts between various methods of data submission. This means that if Briefcase has already been used to submit a form submission to the Aggregate server, then that form will not be duplicated/conflicted if the originating tablet later connects to the internet and submits the form via an internet connection. 

ODK Briefcase can also be used to export csv files via the ```export``` function, meaning that field teams can continue to produce daily reports even when the net is unavailable. 




These instructions are focussed on using a PC/Windows system, but Macs can be used if the [https://www.android.com/filetransfer/](https://www.android.com/filetransfer/) software is installed. 

Our instructions for setting up a Raspberry Pi server are available here [https://github.com/chrissyhroberts/ODK_Pi](https://github.com/chrissyhroberts/ODK_Pi). This platform has the advantage of being pocket sized and can run off minimal power supplies such as mobile battery packs. This makes it useful in conditions where kit-weight, power availability and similar issues could make it difficult to use a laptop.


###Instructions


Ensure that *Asus File Manager* is installed. 
[https://asus-file-manager.en.uptodown.com/android](https://asus-file-manager.en.uptodown.com/android)  

*NB. These instructions are focussed on using the ASUS File Manager, but other file manager apps can probably do the job. You will have to figure out how to use them yourself.*

Open Asus File Manager and navigate to the Internal Storage Folder
Hold down the odk folder until a tick appears to the left of it, indicating that it has been selected
Press the Hamburger button (three dots in the top right corner of the screen)
Select ```Compress```

A box will appear with the message ```Enter the Archive Name```

Change the name to include whichever of the following are appropriate

* Operator name or number  
* Device ID
* Today's date  

		i.e. ODK-Modou-190124

Move the new zip file in to a folder called ```ODK-Zips```  
Select the new zip file (hold down until a tick appears)  
Press the hamburger button and select ```Move to```  
Navigate to ```Internal Storage``` and then ```ODK-Zips``` (you may have to make a new folder if it does not exist (use the plus + key)  
Select ```OK```

Connect the Android device to a PC running ODK Briefcase  
If you need to download ODK Briefcase, find the latest version here [https://github.com/opendatakit/briefcase/releases/latest](https://github.com/opendatakit/briefcase/releases/latest)  
 
A dialog will ask ```Do you want to use USB for file transfer?``` Select 
```Yes```  

Use the windows system to navigate to the ```ODK-Zips``` folder on the device. 
Copy the zip file (i.e. ODK-Modou-190124.zip) to a folder on the PC. 
Keeping this folder organised is very important. 
A sensible design would be similar to this...

	C:/
	->My Documents
	  ->ODK-ZIPs
	    ->Modou
  		    ODK-Modou-190123.zip
  		    ODK-Modou-190124.zip
  		 ->Bubacarr
  		   ODK-Bubacarr-190123.zip
   		   ODK-Bubacarr-190124.zip
  
  
    
Navigate to the ```ODK-Zips``` folder, double click the zip file to see it's contents

Copy the contents of the folder and paste to a folder called ```ODK-Data```. 
Finally rename it from 'odk' to a more descriptive name
i.e. *ODK-Modou-190123*

Keeping this folder organised is very important. 
A sensible design would be similar to this...

	C:/
	->My Documents
  		->ODK-Data
    		->Modou
      			ODK-Modou-190123
      			ODK-Modou-190124
		   ->Bubacarr
		      ODK-Bubacarr-190123
		      ODK-Bubacarr-190124
 
 

###Pulling Data in to ODK Briefcase

Click the ```Settings``` tab and set a storage location for your ODK Briefcase database, for instance ```My Documents/ODK-Storage```

Open ODK Briefcase and navigate to the ```Pull``` tab
Press the ```Configure``` button, navigate to the ```ODK-Data/ODK-Modou-190123``` folder and press the 'open' button.  

You should see a list of forms that can be imported from the folder. Select those you wish to pull.  

Press the ```Pull``` Button  

This will import all data from the folder you selected.   
To add more data to the ODK Briefcase database, repeat this process using other folders in the ODK-Data folder


###Pushing Data to the ODK Aggregate server

*NB. This process works only when online.*  

Select the 'push' tab and press the 'configure' button
Enter the URL, username and password of the aggregate server you wish to push to.
The URL requires that the top folder name of the server is included in the address

i.e. https://test.odk.lshtm.ac.uk/test

Note that the user needs 'form manager' permission on the server.
Select the forms that you wish to push to the server
Press the 'push' button
