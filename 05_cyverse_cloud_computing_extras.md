# Do more with Cloud Computing

## Exercise - Sharing your Atmosphere desktop with another CyVerse user. 

One of the advantages of computing within CyVerse is shared credentials and user profiles on common computing resources. This makes it easy to transfer data, and to enable collaborator access securely. In this exercise, you will share your Atmosphere desktop with another CyVerse user. 

1. Get the username of another CyVerse user and give them your IP address (from the Atmosphere website). 
2. Connect to your Atmosphere instance via VNC. 
3. In your Atmosphere instance, click the **VNC** icon in the upper right-hand corner of the Desktop; this will open a _VNC Server_ window. <br><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_7.jpg", style="width:300px;height:150px;">
4. Click the **More** button on the _VNC Server_ window and select _Options..._; A _VNC Server Options_ window will open.<br><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_8.jpg", style="width:300px;height:350px;">
5. Select _Users & Permissions_ from the _VNC Server Options_ window, then click on **Add**.; Enter the CyVerse username of the collaborator you wish to share with; the click **OK**<br><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/atmosphere_9.jpg", style="width:300px;height:350px;">
6. Make any adjustments to the user permissions, click **Apply**, the click **OK**. Close the _VNC Server_ window. 
7. Your collaborator can now enter the IP address (+“:1”) to their VNC viewer as the server to connect to. They can connect using  their CyVerse username and their user credentials. ## Imaging an Atmosphere instance

Imaging allows you to save a copy of your Atmosphere instance (including data, installed software, etc.). This means that even after your terminate. These instructions give you an overview of the process but you will need to **Read the [Full Documentation](https://wiki.cyverse.org/wiki/display/atmman/Requesting+an+Image+of+an+Instance)**, including which directories will be deleted or overwritten during the process. 

## Working on other Clouds

### Choosing a cloud platform

The most important thing about *The Cloud* is choice - instead of purchasing a physical computer, you can obtain on-demand computing at almost any scale. This power comes with advantages and disadvantages:

**Advantages of Cloud Computing**
* Access large amounts of computing power on demand
* Full administrative rights - install anything
* Use pre-configured images (software already installed)
 

**Disadvantages of Cloud Computing**
* Cloud computing costs money (you must keep track of your costs)
* If you need help, you may not have a local system administrator 
* Images may be poorly documented (you may not be clear on what is installed, or how to use it)

### Cloud platform choices

There are several cloud providers to choose from. Some scientific clouds may either be free or allocate resources competitively. Commercial clouds are can be very powerful, but choice can be overwhelming. We will cover as much as we you need to get through the Data Carpentry lessons, but you will ultimately need to learn things not covered here so see the documentation below:

#### Commercial Clouds

* [Amazon Web Services](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html)
* [Google Cloud](https://cloud.google.com/compute/docs/quickstart)

#### Open Science Clouds
* [Atmosphere](https://pods.iplantcollaborative.org/wiki/display/atmman/Getting+Started)
* [JetStream](http://jetstream-cloud.org/)


## Launching an Cloud Instance (Virtual Machine)


 > **Tip:** Keep in mind, if you are attending a workshop this will have already been done for you!

We will provide instructions for working on the *Amazon* and the *Atmosphere* cloud. Follow the instructions for your platform of choice.

### Launching an instance on Amazon Web Services

**Prerequisites**

* Form of payment (credit card)*
* Understanding of Amazon's billing and payment (See: [Getting started with AWS Billing and Cost Management](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-getting-started.html))
* An image to launch: Amazon maintains a [Catalogue of images ('amis')](https://aws.amazon.com/marketplace/ref=mkt_ste_amis_redirect?b_k=291). 

**In this tutorial:** We will be referring to the Amazon instance used in Data Carpentry's [Genomics Lessons](http://www.datacarpentry.org/lessons/): You can find this on Amazon by searching for: **ami-5bc63136**


*Tip:* You can use some of Amazon Web Services for free, or see if you qualify for an AWS Grant (See: [https://aws.amazon.com/grants/](https://aws.amazon.com/grants/) ) if you are using AWS for education. The free level of service *will not* be sufficient for working with the amount of data we are using for our lessons. 

#### Create an AWS account

1. Go to Amazon Web Services [https://aws.amazon.com/](https://aws.amazon.com/)
2. Follow the button to sign up for an account - you will need to agree to Amazon's terms and conditions and provide credit card information. 


#### Sign into AWS and Launch an Instance
1. Sign into AWS EC2 Dashboard: [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/)
2. Click the 'Launch Instance' button<p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_1.png" width="500"></p>
3. In 'Step 1' you will be asked to choose an Amazon Machine Image (AMI), on the lefthand side, look for 'Community AMIs' and then search for **ami-5bc63136**; select this image
<p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_2.png"width="500"></p>
4. For 'Choose and Instance Type' select **t2.medium**; then click 'Review and Launch' 
<p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_3.png"width="500"></p>  
  
    > **Tip:** You can select larger instances, but these will cost more to run. Also for the 'Review Instance Launch' you will get some warning about instance security. We will not go into detail here about security groups. However, you should know that when you launch an instance, you will want to take steps to make sure no one maliciously accesses your instance. For example, never give your security credentials (next step) to another user.
5. For the 'Review Instance Launch' step, click 'Launch'
6. You will be asked to Select an existing key pair or create a new key pair. Select 'Proceed without a key pair' and select the acknowledgement you are given. Then click 'Launch Instances' 
    <p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_4.png"width="500"></p>

You instance will now be launched. You should follow the links to 'Create billing alerts'. 

#### Connect to Amazon Instance

**Instructions for MAC**

1. Log into your AWC EC2 Dashboard [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/)
2. You should see that you have one instance, to proceed the instance state must be 'running' (if you just launched the instance it will take <5 min for the instance to start running)
 <p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_5.png"width="500"></p>
3. At the bottom of the dashboard, you should see a **Public DNS** which will look something like *ec2.12.2.45.678.compute-1.amazonaws.com*. Copy that address (you may wish make a note of it as you will need this each time you connect. 
 <p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_6.png"width="500"></p>
4. Open the terminal application on your Mac and use 'ssh' to connect. Your command will be:
```bash
    $ ssh dcuser@your.amazon.dns
``` 
5. Your computer will be unable to verify the authenticity of the host... type **yes** to continue connecting
6. Then enter the password for this computer: 'data4Carp'

You should now be connected to your personal instance. You can confirm this with the following commands; ``whoami``,``pwd``,``ls``, which should yield the following results:

```bash
Last login: Thu Jul 30 13:21:08 2015 from 8.sub-70-197-200.myvzw.com
$ whoami
dcuser
$ pwd
/home/dcuser
$ ls
dc_sample_data	FastQC	Trimmomatic-0.32
$ 
```
**Instructions for PC**

1. Download the PuTTY application at: [http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe](http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe)
1. Log into your AWC EC2 Dashboard [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/)
2. You should see that you have one instance, make sure instance state is 'running' (if you just launched the instance it will take <5 min for the instance to start running)
    <p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_5.png"width="500"></p>
3. At the bottom of the dashboard, you should see a **Public DNS** which will look something like *ec2.12.2.45.678.compute-1.amazonaws.com*. Copy that address (you may wish make a note of it as you will need this each time you connect. 
    <p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_6.png"width="500"></p>
4. Start PuTTY. In the section 'Specify the destination you want to connect to' for 'Host Name (or IP address)' paste in the DNS address and click 'Open'
5. When prompted to login as, enter 'dcuser'; you may be notified that the authenticity of the host cannot be verified - if so, ignore the warning an continue connecting
6. When prompted for a password enter 'data4Carp'

You should now be connected to your personal instance. You can confirm this with the following commands; ``whoami``,``pwd``,``ls``, which should yield the following results:

```bash
Last login: Thu Jul 30 13:21:08 2015 from 8.sub-70-197-200.myvzw.com
$ whoami
dcuser
$ pwd
/home/dcuser
$ ls
dc_sample_data	FastQC	Trimmomatic-0.32
$ 
```

#**Very Important Warning - Avoid Unwanted Charges**
Please remember, for as long as this instance is running, you will be charged for your usage. You can see an estimate of the current charge from your AWS EC2 dashboard by clicking your name (Account name) on the upper right of the dashboard and selecting 'Billing & Cost Management'. **DO NOT FORGET TO TERMINATE YOUR INSTANCE WHEN YOU ARE DONE**

### Terminating your instance

When you are finished with your instance, you must terminate. Follow the following steps. 

1. Sign into AWS and go to the EC2 Dashboard: [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/)
2. Under 'Resources' select 'Running Instances'
3. Select the instance you wish to terminate, then click 'Actions'
    <p><img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/logging-onto-cloud_7.png"width="500"></p>
4. Under 'Instance State' select terminate. 

    > **Warning:** This will delete any data on this instance, so you must move any data you wish to save off the instance.

    >  **Tip:** You can use iCommands to move data between your computer, a cloud instance, and the iPlant Data Store. iCommands is installed on the Data Carpentry Amazon AMI. You can download and see documentation for iCommands [here](https://pods.iplantcollaborative.org/wiki/display/DS/Using+iCommands) - there is also some documentation on setting up iCommands in the Atmosphere section below
5. Select 'Yes, Terminate' to terminate the instance. 

