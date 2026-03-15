# Remote-Administration

<h1>Overview: Lab 8 Windows 10 Remote Access: Remote Desktop, Remote Registry</h1>

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




   
