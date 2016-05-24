# Introduction to Atmosphere Cloud Computing

[Atmosphere](http://www.cyverse.org/atmosphere) is one of the most versatile components of the CyVerse CI. Anything that you would normally be able to do with your local laptop/desktop, you can do on a virtual machine in the Atmosphere cloud. The advantage of using Atmosphere is that you can get access to greater resources (currently up to 16 CPU, 128GB RAM machines). Additionally, those resources are co-localized with the CyVerse Data Store so that moving to and from your instance is very easy to do. ## How to launch and connect to an Atmosphere instanceCreating an Atmosphere instance is like buying a new computer, you will have to select what you want and then customize it to suit your needs. Also like a new computer, your Atmosphere instance will generally come only with the listed software installed. You will have to connect that instance to your CyVerse Data Store to import files. This guide will not cover all the use cases and features of Atmosphere (e.g. managing your allocation, requesting more resources, Imaging, and creating and mounting volumes). See the [Atmosphere manual](https://pods.iplantcollaborative.org/wiki/display/atmman/Getting+Started).

>**Tip:** To use Atmosphere, you must have an email address from an academic/governmental institution and request access to Atmosphere through the user portal.  To request access, login to user.iplantcollaborative.org and check to see if Atmosphere is listed under ‘My Services.’ If it is not, scroll down and click the “Request Access” button next to Atmosphere to complete a request form. ### Launching an Atmosphere instance

1.	Login to Atmosphere 2.	Click **Launch New Instance** either on the navigation panel (left) or on the home screen.<br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_1.jpg", style="width:150px;height:180px;">   3.	In the search window, search and select the image you wish to use ( **Note:** Some images support a GUI Desktop and some are only accessible through the shell – check the description and/or tags)<br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_2.jpg", style="width:450px;height:150px;"> 4.	Click **Launch**; during the launch wizard you may name your instance, select the cloud to launch on, the size of the instance, and a project to associate this instance with. If you do not have an existing project, you must create one during this launch. Follow the launch wizard through to the end and click ‘**Launch Instance**’. Your instance should be ready in 10-20 minutes. <br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_3.jpg", style="width:300px;height:320px;"> 

### Connecting to Atmosphere instance via SSH

> **Tip:** Your Instance status must be ‘active’ in order for you to connect. Windows users can download [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) to connect via the terminal.1.	Locate your Instance IP address in the Atmosphere control panel
2.  Open a terminal (Mac/Linux) and connect `$ ssh your_cyverse_username@cyverse.org`
3. You will be asked to save and RSA key to the list of known hosts, enter ‘yes’
4. When prompted, enter your CyVerse password.<br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_4.jpg", style="width:600px;height:375px;"> 

### Connecting to Atmosphere instance via VNC

Some Atmosphere images also are configures with a desktop interface. This can be accessed using a VNC Viewer. Download VNC Viewer from Real VNC to connect to your instance. 

> **Tip:** When you download VNC viewer, the program will ask for an IP address. This IP address is available from the Atmosphere website; log into Atmosphere and locate the IP address of the instance you wish to connect to. 

**VNC Connection Window**<br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_5.jpg", style="width:300px;height:175px;">

1. Locate your Instance IP address (next to your instance name)<br><img src="hjacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_6.jpg", style="width:480px;height:100px;">2.	Enter your **IP address + “:1”** in the ‘VNC Server’ field (e.g. 161.803.39.887:1) and click connect. 3.	When connecting for the first time to an instance, you will be prompted to save a signature. Select yes and continue; you will then be connected to your Atmosphere desktop. 

## Exercise - Sharing your Atmosphere desktop with another CyVerse user. 

One of the advantages of computing within CyVerse is shared credentials and user profiles on common computing resources. This makes it easy to transfer data, and to enable collaborator access securely. In this exercise, you will share your Atmosphere desktop with another CyVerse user. 

1. Get the username of another CyVerse user and give them your IP address (from the Atmosphere website). 
2. Connect to your Atmosphere instance via VNC. 
3. In your Atmosphere instance, click the **VNC** icon in the upper right-hand corner of the Desktop; this will open a _VNC Server_ window. <br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_7.jpg", style="width:300px;height:150px;">
4. Click the **More** button on the _VNC Server_ window and select _Options..._; A _VNC Server Options_ window will open.<br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_8.jpg", style="width:300px;height:350px;">
5. Select _Users & Permissions_ from the _VNC Server Options_ window, then click on **Add**.; Enter the CyVerse username of the collaborator you wish to share with; the click **OK**<br><img src="jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_9.jpg", style="width:300px;height:350px;">
6. Make any adjustments to the user permissions, click **Apply**, the click **OK**. Close the _VNC Server_ window. 
7. Your collaborator can now enter the IP address (+“:1”) to their VNC viewer as the server to connect to. They can connect using  their CyVerse username and their user credentials. 