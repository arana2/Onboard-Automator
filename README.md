# Onboard-Automator
This project aims to streamline and automate the onboarding process for new employees into Azure Entra ID (formerly known as Azure Active Directory), while also automatically assigning the necessary Azure resources required by the new employee.

**Detailed Description**

This project automates the onboarding process for new employees. It begins when a new employee submits their information through a web form via Logic Apps. This triggers the Azure Logic App to create a new user in Entra ID and assign them to the Information Technology group. The Information Technology group will have Local Administrator access to (2) virtual machines.


**Azure Services Used:**
- Azure Entra ID
  - Stores the created user
  - Assigns user to a designated group
- Azure Logic Apps
  - Automates the process of collecting the new employee information -> creating the new user -> assigning user to a group -> sending a welcome email to the new employee
- Azure Email Service (part of Logic Apps connector)
  - Responsible for sending welcome email to user
- Azure Resource Groups
- Azure Virtual Machines
 - The created user assigned to the Information Technology group will have access to (1) Azure Windows 11 Pro virtual machine and (1) Linux Ubuntu Server virtual machine
 - Virtual Machine Administrator Login Role assignments are assigned to the Information Technoology Group at the VM Level

Steps

1. 

Project Workflow
Image goes here

Reference:
https://github.com/madebygps/projects/blob/main/az-104/onboarder.md

**Azure Logic Apps **is a cloud service provided by Microsoft Azure, enabling users to build and execute workflows for automating business processes and integrating diverse services and applications. A Logic App workflow consists of a sequence of steps designed to automate a specific task or process. In this instance, I have developed a Logic App workflow. Initially, I select a trigger, which could be an event such as a new employee record in a SharePoint list or an incoming email to a designated mailbox. This allows me to test and demonstrate the functionality of the automation. Once the trigger event occurs, the Logic App workflow is activated.
