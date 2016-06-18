# Managing Data with Atmosphere

When your Atmosphere instance is available, it will only contained the software and data that is part of the actual image. You will need to import datasets from your Data Store in order to work on them. 

## Import data using iCommands

iCommands is a collection of commands for Unix and Mac that are used in the iRODS system to interact with the CyVerse Data Store. Many commands are very similar to Unix utilities. For example, to list files and directories, you use `ls` in Linux, but in iCommands you use `ils`.


While iCommands are great for all transfers and for automating tasks via scripts, they are the best choice for large files (2-100 GB each) and for bulk file transfers (many small files). For a comparison of the different methods of uploading and downloading data items


### Downloading and configuring iCommands

iCommands is available for Mac and Linux. You must download the binaries and configure them for use. We will not cover all of the iCommands here but some important resources include:

- Full CyVerse [iCommands Documentation](https://pods.iplantcollaborative.org/wiki/display/DS/Using+iCommands)
- iRODS official [iCommands Documentation](https://docs.irods.org/master/icommands/user/)

#### Download iCommands

1. Select the iCommands binary for your platform:
    - For Mac: Download the [Mac binary](https://www.irods.org/binaries/irods3.3.icmds.mac.intel.tar).
    - For Linux: Download either the Linux [64-bit binary](http://www.iplantcollaborative.org/sites/default/files/irods/icommands.x86_64.tar.bz2) or the Linux [32-bit binary](http://www.iplantcollaborative.org/sites/default/files/irods/icommands.i386.tar.bz2).
2. Untar/decompress the download (e.g. `mkdir icommands && tar -xvf irods3.3.icmds.mac.intel.tar -C ./icommands`)

> **Tip:** You may wish to add iCommands to your path  information on how to add the resulting iCommands directory to your $PATH, see UNIX / Linux: [Set your PATH Variable Using set or export command](http://www.cyberciti.biz/faq/unix-linux-adding-path/)

#### Configure iCommands

In a terminal window, enter the following to initialize iCommands and your Data Store connection.

1. Initialize iCommands using the `iinit` command 
2. You will then be asked to setup your account and will need to enter the following information

|Prompt|Entry|
|------|-----|
|irodsHost|data.iplantcollaborative.org|
|port|1247|
|zone|iplant|
|irodsUserName|your CyVerse username|
|Current iRODS password|your CyVerse password|

> **Tip:** Verify that you have connected to your iPlant Data Store; view the contents of your home directory using the following the `ils` command. 


### Uploading and downloading with iCommands

#### Downloading from Data Store

Use the *iget* command to move files from the Data Store into your remote machine:
```
$ iget -P datastore_file.txt .
```
There are several other iCommands options (including how to use the -T option for more reliable big data transfers, and -r command for recursive transfers of directories - See [iCommands documentation](https://pods.iplantcollaborative.org/wiki/display/DS/Using+iCommands). 

#### Uploading to Data Store

To move data from a local source to the Data Store use the *iput* command. In this case we pass the -P option to see the progress of the transfer. 
```
$ iput -P remote_machine_file.txt .
```
**Tip:** in this case, the '.' stands for the current CyVerse working directory which is by default '/iplant/home/your-cyverse-username'

## Import data using iDrop


1. Select the iDrop icon on your desktop
2. Depending on your the version of iDrop used, you may be prompted for a “pass phrase” – since this step does not allow authentication into your Data Store account a simple, memorable phrase is all that is required. If you are only asked for a username and password – simply enter your CyVerse username and password and continue this guide at step 6
3. Click the  (Add User) icon to connect iDrop to the iPlant Data Store
<img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/add_user_icon.jpg", style="width:20px;height:20px;">
4. If you are prompted to “Create Grid Account Information” enter the following (paying attention to capitalization) and entering your CyVerse credentials where required:
 
    |Prompt|Entry|
    |------|-----|
    |Host|data.iplantcollaborative.org|
    |Port|1247|
    |Zone|iplant|
    |User|your CyVerse username|
    |Password|your CyVerse password|
    |Default Resources|iplantRG|
    
5. Select the data.iplantcollaborative.org line for your host and then lick click the authentication icon <img src="https://jacksonlab-workshop-2016.readthedocs.io/en/latest/img/authenticate_icon.jpg", style="width:20px;height:20px;">   to access the data store. One first setup you may wish to select the “Show GUI at Startup.” option if prompted. 
6. To upload – select the place on your local computer (left column) where the files are located: - Windows – select your hard drive (e.g. C:\) and then navigate your directory
 - Mac/Linux – select the files or folder you wish to move (most items will be in the /home directoryThen drag the file(s) or folder(s) you wish to transfer into your iPlant Data Store (right column). 7. To download – select the file(s) or folder(s) in your Data Store and drag them to a location on your local computer (left column). To upload data to the Data Store drag the item from a location on your local computer (left column) to the Data Store (right column). 