# Remote-Administration

<h1>Overview: Lab 8 Windows Remote Administration</h1>

This segment of my home lab documentation is dedicated to the setup and utilization of **Remote Desktop** and **Remote Registry** for accessing a **Windows 10** machine within a VirtualBox environment. The project outlines the procedures for enabling, configuring, and troubleshooting remote access services, enabling both users and administrators to connect to and manage a Windows 10 PC from a distance.

<h2>Goals</h2>

1. **Windows 10 Remote Management:** Setting up and overseeing remote access to Windows 10 systems.
2. **Remote Registry:** Investigating the **Remote Registry** feature to control registry settings from a different computer.
3. **Remote Desktop:** Configuring and employing **Remote Desktop** for secure remote management of Windows 10 systems.
4. **C$ Administrative Share:** Gaining insight into and utilizing the concealed **C$ administrative share** for file and system access.


<h2>Documentation</h2>

In this home lab, our focus will be on utilizing Windows 10 Remote Management, Remote Registry, Remote Desktop, and accessing C$. We will start by enabling Windows 10 Remote Desktop Services on Desktop2 for Bob. On Desktop2, launch File Explorer, right-click on "This PC," and choose "Advanced System Settings." Then, with your Helpdesk administrative permissions, enable "Allow Remote Connections" and click on "Select Users" to include the required users.






1. ![Remote Access 1](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%201.jpg?raw=true)

Choose "Add", then include Helpdesk, followed by selecting "OK" and then "Apply".

2.![Remote Access 2](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%202.jpg?raw=true)
   
With Remote Desktop now activated, we can proceed to the Helpdesk account. Begin by searching for "Remote Desktop Connection" in the Windows search bar and launch the application. In the "Computer" field, enter "Desktop2" and sign in with your Helpdesk credentials. After the remote session is established, you may choose "Yes" to terminate Bob's session, enabling you to access Desktop2 using the Helpdesk account.

3.![Remote Access 3](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%203.jpg?raw=true)

Now that we are accessing Bob's computer remotely through the Helpdesk account, we can carry out several tasks. For instance, we can create a new folder for Bob by going to his folder, then opening the "Desktop" directory and creating a folder in that location.

4.![Remote Access 4](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%204.jpg?raw=true)

We can also remove items from Bob's downloads folder if Bob wishes to.

5.![Remote Access 5](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%205.jpg?raw=true) 

We can access Bob's AppData folder by going to User → Bob and entering \appdata in the search bar of File Explorer. This will enable us to view and manage the files within Bob's AppData directory.

6.![Remote Access 6](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%206.jpg?raw=true) 

Let's terminate the Remote Desktop Connection and re-establish it as Bob on Desktop2. After logging in, we should be able to view the "Test" folder on Bob's desktop.

7.![Remote Access 7](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%207.jpg?raw=true) 

Next, we will demonstrate how to identify shared drives. On Desktop2, launch Command Prompt (CMD) and enter the command net use. This will present a list of all the network drives that are currently mapped to the system.

8.![Remote Access 8](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%208.jpg?raw=true) 

An alternative method to identify shared drives is to enter "Services" in the Windows search bar and execute it as an Administrator. Utilize Helpdesk credentials to gain access. In the Services window, locate "Remote Registry," right-click on it, and choose "Properties." Modify the "Startup type" from "Disabled" to "Automatic," then click "Apply" and "OK." Subsequently, click "Start" to activate the Remote Registry service. This will grant access to registry information, which includes shared drives.

9.![Remote Access 9](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%209.jpg?raw=true)

Now, let's access our Helpdesk account and search for "Registry Editor".

10.![Remote Access 10](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2010.jpg?raw=true)

Choose File from the top left corner → Connect to Network Registry → then look for "Desktop2" and click "OK".

11.![Remote Access 11](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2011.jpg?raw=true)





12.![Remote Access 12](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2012.jpg?raw=true)

Within HKEY_USERS, we must navigate through the directories to locate the folder linked to the "Z" drive found in the "Network" section. This will display the shared drives that are mapped to the system. The drive letter "Z" will appear in the registry key related to the network shares, assisting in identifying the shared drives connected to the computer.

13.![Remote Access 13](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2013.jpg?raw=true)


Now, we will utilize the C$ command with our Helpdesk account, enabling administrators to remotely access the root of the C: drive on the local user account. To accomplish this, open File Explorer on Helpdesk and enter \Desktop2\c$ in the search bar, then hit Enter. This action will provide remote access to the C: drive of Desktop2.

14.![Remote Access 14](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2014.jpg?raw=true)

At this point, we can proceed to delete the "Test" folder that we created remotely. Navigate to Users → Bob → Desktop, and find the "Test" folder. After locating it, just delete the folder to eliminate it from Bob's desktop.


15.![Remote Access 15](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2015.jpg?raw=true)

Upon reviewing Bob's computer, we observe that the "Test" folder has disappeared from Bob's desktop.


16.![Remote Access 16](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2016.jpg?raw=true)

An alternative method to access a user's system remotely is by utilizing Windows Remote Assistance. To do this, type "Windows Remote Assistance" in the Windows search bar on Desktop2, and then choose the option "Invite someone you trust to help you."


17.![Remote Access 17](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2017.jpg?raw=true)

Choose "Save this invitation as a file" on your desktop.


18.![Remote Access 18](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2018.jpg?raw=true)

Now, return to the Helpdesk account, launch Windows Remote Assistance, and choose Help Someone Who Has Invited You. In the prompt, enter \Desktop2\C$ to reach the invitation file. Once connected, go to Users → Bob → Desktop to find the invitation file. Subsequently, you can input the password given in the invitation to initiate the remote session.


19.![Remote Access 19](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2019.jpg?raw=true)

A prompt will inquire whether we wish to permit Helpdesk to access remotely; choose "Yes"


20.![Remote Access 20](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2020.jpg?raw=true)


We now have remote access to Bob's computer via Helpdesk.


21.![Remote Access 21](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2021.jpg?raw=true)

We can now send messages to Bob and request control access from the top left.


22.![Remote Access 22](https://github.com/RedFORce1994/Remote-Administration/blob/main/Remote%20Administration%20Part%2022.jpg?raw=true)



Congratulations! we have successfully access **Windows 10 Remote Management e**xploring the Remote Registry feature, setting up and utilizing Remote Desktop for secure remote control of Windows 10 system and using **C$.**
