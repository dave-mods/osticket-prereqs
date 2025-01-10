# osticket-prereqs<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Here in this tutorial I will show you prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)


<h2>Installation Steps</h2>

First you want to get logged into Azure.
![image](https://github.com/user-attachments/assets/5aecbd81-e2d4-4aed-8a5b-8f141cb63143)

In the Virtual Machines tab we are going to click create and then click Azure virtual machine.
![image](https://github.com/user-attachments/assets/f1b2affd-d8d0-484d-8b29-d769aeda4403)

Here we will be setting up the VM. We can create a resource group here, as you can see. Just click Create New and type OsTicket. Name it osticket-vm. Select Windows 10 Pro, version 22H2-x64 Gen2. I used Canada Central for my region, so I could get the proper size with 2 vcpus, 8 GiB memory. Use whatever works for you as long as you have this size available.
![image](https://github.com/user-attachments/assets/056168fa-71cc-4b90-9b15-7c870a2ac362)

Here we will set the username to "labuser" and the password to "Osticketpassword1". Also make sure you check the Licensing box at the bottom, or it will fail to set up the VM and you will have to repeat this and then check the box. After you check the box, you are ready to click "Review + Create".
![image](https://github.com/user-attachments/assets/dab0a60c-e45f-4b25-8348-15b6daedec3e)

If you have done everything correctly to this point, you should see this screen and then click "Create" again at the bottom.
![image](https://github.com/user-attachments/assets/0e62da97-d65f-4b33-9ce0-c3e9c9d74c04)

This shows us our VM is done being created.
![image](https://github.com/user-attachments/assets/e2449139-2969-4e35-b46c-6cc901b20671)

Here we will login to our VM using Remote Desktop. Copy the Public IP address of your VM and paste it into the Remote Desktop Connection then click connect.
![image](https://github.com/user-attachments/assets/45d80d62-1246-4b40-b332-9ff7df54c0ac)

Here we will enter our "labuser" username and our "Osticketpassword1" password from earlier. If a box pops up click "Yes" and it will log you into the VM.

![image](https://github.com/user-attachments/assets/9b50fc03-3c2b-4130-b9c7-458f6edc1e1b)

Uncheck all the boxes as we don't need any of this.
![image](https://github.com/user-attachments/assets/d9e0a197-e6fd-4a04-b302-fb5cc1b7d9e8)

Open up Microsoft Edge and uncheck all the boxes and choose continue without data as you go through the prompts till you are at the home page.
![image](https://github.com/user-attachments/assets/ca2e661a-f6f9-4e17-a2a6-505092b584ee)

We will download the OsTicket file and move it to the desktop and then right click it and extract all.
![image](https://github.com/user-attachments/assets/7454b164-6993-4ff5-9008-4eeacd7388d2)

Go to the search bar at the bottom of the screen and type in Control Panel and open it up.
![image](https://github.com/user-attachments/assets/ad26b9ee-341d-45b9-8ca4-e5c13daa4925)

Under the Programs click the "Uninstall or change program" button then select the "Turn Windows features on or off" on the left hand side.
![image](https://github.com/user-attachments/assets/9b297f21-73aa-4f0c-af34-a0f282cfa26a)

In this box we will check the "Internet Information Services" box and expand it. Then expand "World Wide Web services", "Application Development Features" and check the CGI box and then click "OK".
![image](https://github.com/user-attachments/assets/d1121268-33db-4727-ab80-8e05834a4a83)

In your browser type in 127.0.0.1 and search it. If you get this screen then you have done all the steps right. We have now enabled IIS.
![image](https://github.com/user-attachments/assets/92c0d3e8-84db-431e-9660-0f706c81e166)

Next we will install PHP manager for IIS setup. Go into the OsTicket file we unzipped earlier and double click PHPManager and install it.
![image](https://github.com/user-attachments/assets/743ebd9d-229f-4ef4-a7e4-bf6b9dc94722)

Next install the "rewrite" file
![image](https://github.com/user-attachments/assets/1869d263-a155-4365-bf44-a08d721cc004)

Right clcik the folder on the task bar and choose "File Explorer" then choosen "This PC" and then double click C drive and right click and make a new foilder and name it PHP.
![image](https://github.com/user-attachments/assets/8893b940-8d89-42dd-91f3-798d4539cbe0)

Go to the OsTicket installation folder and right click PHP zip folder and click extract. Search PHP for the destination and click extract.
![image](https://github.com/user-attachments/assets/0aeba5a5-03e7-4a07-8ecb-634edd48b83b)

Our next step is to install the VC_redist file. Double click it, Agree, then install.
![image](https://github.com/user-attachments/assets/5925fc06-1885-497d-8027-5e33787f0bcc)

Now install mysql. double click it and go through the install. When it asks setup type select Typical. Then Standard Configuration.
![image](https://github.com/user-attachments/assets/5915f6b0-9f7c-4081-9396-e908960d73c4)

For this box type in "root" for both. DO NOT MESS THIS PART UP. Then in the next box don't click any of the options just Finish.

![image](https://github.com/user-attachments/assets/02a7df1f-9001-4146-97e4-2d81194d818c)

We can then go to Start and search IIS and right click and pick Run as Admin.

![image](https://github.com/user-attachments/assets/bc906c60-aa55-445c-922a-f4373b8ec5d8)

Here we will double click PHP Manager, Register new PHP version, browse to C drive, open PHP folder and double clcik php-cgi then click OK.
![image](https://github.com/user-attachments/assets/589cb4d6-310d-49a4-a350-c5cab425a420)

After that is finished click the osticket-vm on the left. Then on the right sride we will want to click the Restart button.
![image](https://github.com/user-attachments/assets/a62905d0-1590-4b4e-8581-0d2de5d4a7d8)

Now we can jump back to our osTicket-Installation folder and unzip the osTicket folder. It will make a new unzipped folder at the top.
![image](https://github.com/user-attachments/assets/ace7d65c-8dc4-49d8-b722-8db186a93e9c)

Open a new file explorer go to the C drive open the inetpub folder then down to the wwwroot folder. Open the wwwroot folder. You will want to right click and copy the upload folder and then paste it into the wwwroot folder. We will now rename the upload folder to "osTicket".
![image](https://github.com/user-attachments/assets/0bf7ec66-df91-4e7e-b8e6-ec63eabd36dc)

Open IIS and Restart it.
![image](https://github.com/user-attachments/assets/02b5c7c8-aa4f-4c77-9741-9440e09c68eb)

On the left side expand, Sites, Default Web Site and then click osTicket. On the right side click browse and it will load osticket in the web browser.
![image](https://github.com/user-attachments/assets/cda7a728-fb1d-4dda-804d-13096c646de8)

So to enable some settings go to the osTicket folder in IIS manager and open PHP manager. Under PHP Extensions click the Enable or disable an extension button. We will enable "php_imap, php_intl, php_opcache". Once done refresh the osticket webpage and examine changes.
![image](https://github.com/user-attachments/assets/af99e592-9fe9-4fc2-8008-f0be1058e014)

Now we need to go back into the C drive, inetpub, wwwroot, osTicket, include, then look for ost-sampleconfig.php and rename it to ost-config.php.
![image](https://github.com/user-attachments/assets/4d5b90fa-02ef-4254-9fed-17f628a9a825)

Next right click ost-config.php and select properties, Security and then Advanced. Select disable inheritance and select Remove all.
![image](https://github.com/user-attachments/assets/1e963bae-493d-4d59-9f67-04c72051c147)

Now we will click Add, Select a principal and then type "everyone" and hit check names and click OK then check the Full control box and then hit OK.

![image](https://github.com/user-attachments/assets/e0093ada-0a37-4575-9ce9-76d4bc4b1f8a)

Go back to osTicket installer and continue. We will now fill out all the information needed. Under Admin User we will use "adminuser" for our user name and "Password1" for our password.
![image](https://github.com/user-attachments/assets/cdc6808d-9d73-49ae-aee6-9d465f4cda51)

Before we continue we have to setup the data base using HeidiSQL. Go to the osTicket install file on  your desktop open the file and go to HeidiSQL and intall it.
![image](https://github.com/user-attachments/assets/21e4db4f-fe86-4cc1-9359-70b0e34c2544)

Inside HeidiSQL click New in the bottom left corner. Remember our password for here was "root" and click open.
![image](https://github.com/user-attachments/assets/cfb7ca5a-6884-48d9-866a-1f9a325e3f21)

In HeidiSQL we need to make a data base. Right click unnamed go to new and select data base. For the name we will enter "osTicket" and hit OK.
![image](https://github.com/user-attachments/assets/116341b7-a4f4-4e3d-8f86-c159a7c0159f)

Back in osTicket installer in database settings we will put "osTicket" under MySQL Database and then username and password will be "root" and "Password1".
![image](https://github.com/user-attachments/assets/5b1f8511-a3bb-4e4d-a506-4718a9cdb507)


Congratulations!!! You have fully setup osTicket.
![image](https://github.com/user-attachments/assets/2a0d73b1-853b-4c44-914d-47e67a3a19d6)



In the next section I will show you how to setup agents, users and how to give them permissions and more.
