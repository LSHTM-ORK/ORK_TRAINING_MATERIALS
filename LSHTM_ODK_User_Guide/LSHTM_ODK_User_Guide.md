<img src="./Files/LSHTM__Global_Health_Analytics_logo copy.png" alt="drawing" width="400"/>
</Br>

## LSHTM ODK Server Setup Guide

**version 3.0.1 -- 2022-11-03**

</Br></Br>


## Introduction

* The majority of the support you will need to use ODK can be found in the official ODK documentation at [https://docs.getodk.org/](https://docs.getodk.org/). There you will find instructions that are both comprehensive and very well maintained by the ODK Community [https://forum.getodk.org/](https://forum.getodk.org/).

* This document provides an overview of the specific requirements for setting up and configuring an ODK Server through LSHTM's system, run by the LSHTM Global Health Analytics group in collaboration with   

* More information about other services provided by the LSHTM Global Health Analytics group can be found on our project website [odk.lshtm.ac.uk](odk.lshtm.ac.uk)

* Email queries to [*odk@lshtm.ac.uk*](mailto:ODK@LSHTM.AC.UK)
  


### Setting up your server


- 	**Request an ODK Server** at LSHTM by completing [this form](https://docs.google.com/forms/d/1fR-hyt3KY3dqrRyFeoKOx0DvBHm1LBc3Q1LVG9GmPWU/edit?usp=forms_home&ths=true]).  

- Each ODK project server is only for use by your team and for the specific project named in the server request form.  

- You will receive an email from `no-reply@lshtm.ac.uk` which will invite you to become a `web user` on ODK Central, the software server that runs ODK. The email will contain a link to the ODK Central server system. *This link will expire after 24 hours.*
- Click the link and you will be taken to a page where you can set your password. 

 	- A good technique for making passwords is to use four random words, put together in a memorable way
		- For instance ```grapes$CATCH£brickRED*fudge``` is a strong and memorable password. 
 		- Do not use simple replacement logic like this ```cl3v3r-pa55w0rd``` as passwords generated this way are easily cracked
 		- Please note that passwords should NOT include the name of your project, nor the year it started (i.e. `covidcomplications2020` would be a **very bad** password)

- Once you have signed in, you should see the welcome page and a list of projects that you have been assigned to as a user or project administrator. Any user can be assigned to multiple projects, but projects can only be created or archived by the system administrators. If you want to set up additional projects, then you should complete a new server request form.

 <img src="./Files/central_welcome.png" alt="drawing" width="400"/>
</Br>

- If you click on the name of the project (here `Default Project`) you will be taken to the project page, which is where you will do most of the work. On this page you can add and test data collection forms, create and control access for users for the ODK Android app, or make URLs that will allow data collection via web-forms. The project page looks like this

 <img src="./Files/central_project_view.png" alt="drawing" width="400"/>
</Br>
 
 
### User types

ODK Central has two types of users, these being `web users` and `app users`. 

- `Web users` are able to log in to the ODK Central server and carry out administrative tasks such as adding new forms and creating and managing `app users` and webforms. Only the LSHTM system administrators can add new `web users` to the system, but any web user who currently has an account with ODK central can be invited by the project administrator to join their project. In most cases we expect web-users to be LSHTM staff, students and honorary appointees.

- `App users` have primarily data collection roles and can not access the server website. App users may include field enumerators and partners outside LSHTM.

### Adding additional users

[App users](https://docs.getodk.org/central-users/#managing-app-users) are people who can submit data to ODK Central via the ODK Collect app. Project managers can add as many app users as they like. 

[Web users](https://docs.getodk.org/central-users/#managing-web-users) are people who are authorised to use ODK Central’s web interface. There are [different roles](https://docs.getodk.org/central-users/) for web-users, but only system admins can add web-users to your project. To add web users, please contact [odk@lshtm.ac.uk](mailto:odk@lshtm.ac.uk), providing the name, institute and role required for each user. For data security purposes you should aim to minimise the number of web-users who have higher levels of access to your data. 

[Public access links](https://docs.getodk.org/central-submissions/) can be created by web users. These links can be used by participants to submit data through a web browser. They are particularly useful for online surveys.


### Initial project settings

Before you can start collecting data, you have to change some settings. From the project page, click the `settings` tab. Here you have three options.

 <img src="./Files/central_settings.png" alt="drawing" width="400"/>

* **Archive** this project
	* This is used at the end of the study. Archiving is irreversible, so unless you are sure that you are done, don't press this button.
* **Rename** 
	* You will see the option to rename your project but **This should not be done under any circumstances**. The LSHTM system administrators use the project names to audit the use of our services across the platform and any projects which are renamed by users will be deactivated immediately.
* **Encryption**
	* Encryption protects your data and is encouraged, but before you proceed with setting this up, read the rest of this document.
	

### Please note the following very important points

* Important system updates (for instance if our servers go down unexpectedly) will be announced through our Twitter account [@LSHTM_GHA](https://twitter.com/LSHTM_GHA)

* The project name should not be changed under any circumstances
 

### Data Security

- ODK Central data are encrypted at rest. This means that when you are not logged in, your data are safe.

- Data are stored on institutional servers in LSHTM’s data centres at Keppel St and Tavistock Place. All data are backed up according to LSHTM’s institutional policy.

- You should always log out of the Central server at the end of each session and should not save your password in your browser’s ‘remember password’ options

- Central has options for enhanced data protection through project level encryption. Please read about these options [here](https://docs.getodk.org/central-encryption/#central-encryption-modes) and think about whether using project level encryption is appropriate for your work; noting that some features of ODK, such as editing submitted data are disabled by project level encryption. In many cases we recommend turning this feature on unless you need to edit data longitudinally via Central’s Enketo Webforms. 

Who can see your data?

* If you use project level encryption, 

	* Only you and those who know the decryption password can view your data
	* You can only view and manage data after downloading it
	* Some features of ODK are disabled (on server editing through Enketo webforms, OData links etc)
	* This is the best option for high security and zero-trust contexts, and for simpler data collection approaches

* If you do not use project level encryption

	- Only those who have a role that allows data viewing - see [here](https://docs.getodk.org/central-users/) 
	- Note that LSHTM ODK Central system administrators are included in this group
	- **LSHTM’s system admins (n = 3) require reasonable access to projects for service provision, but will never access your data sets for reasons other than service provision or to respond to requests for project support**
	- This is the best option for work that involves management of forms across time and for entity-based research



### Fair Usage

The Central server is a shared resource that is used by hundreds of projects. Whilst the server is able to handle very large projects without other users seeing performance drops, the system can become unstable when there is very high demand for data transfers from the server to client machines. This usually occurs when users request large amounts of data with high frequency.

Users should not therefore attempt to create real-time data links, or to build real time dashboards that utilise data from the Central server. If you plan to create any kind of dashboard that pulls data directly from the Central server, you should first discuss this with our team via [odk@lshtm.ac.uk](mailto:odk@lshtm.ac.uk). Dashboards should update at most once a day, preferably between 0000 and 0500 UTC. 

Users in violation of this policy may have their accounts suspended without warning. 

### Before starting data collection you will need

* Ethical consent
* A data management plan
* A data protection impact assessment
	* Information on data protection at LSHTM can be found [here](https://lshtm.sharepoint.com/Services/Information-Management/Data/Pages/default.aspx)
* If you need support for data protection issues, please contact the LSHTM Data Protection Officer at [DPO@lshtm.ac.uk](mailto:DPO@lshtm.ac.uk)
 
## Pay What You Can

If you would like to support our activities with a pay what you can (PWYC) payment, this can be actioned via an inter account journal transfer (IAJT) to our **project code ITCR052210** using account code 1300. Please note that some funders (EC, UKRI, WT and US Fed) may not allow this type of payment, so you should check with your administrators before making any PWYC payments.
 



 **PLEASE NOTE** 


* GDPR makes no clear distinction between the use of names and pseudonyms or ID codes. Any data which can be linked to a living individual (by any person) is considered sensitive and 'relevant' to the GDPR. 

* Fully anonymous data sets (for instance where the project leads cannot link the data back to the origin in any way) are exempt from GDPR.  



## Consult the ODK Documentation for further instructions

* Your project should now be up and running.  

* For further instructions on how to use ODK, please refer to the official ODK documentation at [https://docs.getodk.org/](https://docs.getodk.org/).  

<Br>  
<div style="page-break-after: always;"></div>  


<Br><Br><Br><Br>








