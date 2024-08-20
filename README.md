# Onboard-Automator
This project aims to streamline and automate the onboarding process for new employees into Azure Entra ID (formerly known as Azure Active Directory), while also automatically assigning the necessary Azure resources required by the new employee.

**Detailed Description**

This project automates the onboarding process for new employees. It begins when a new employee submits their information through a web form via Logic Apps. This triggers the Azure Logic App to create a new user in Entra ID and assign them to the Information Technology group. The Information Technology group will have Local Administrator access to (2) virtual machines.

**Azure Services Used:**
- Azure Entra ID:
  - Stores the created user.
  - Assigns the user to a designated group.

- Azure Logic Apps:
  - Automates the process of collecting new employee information, creating the new user, assigning the user to a group, and sending a welcome email to the new employee.
Azure Email Service (part of Logic Apps connector):
  - Responsible for sending a welcome email to the user.

- Azure Resource Groups

- Azure Virtual Machines:
  - The user created and assigned to the Information Technology group will have access to (1) Azure Windows 11 Pro virtual machine and (1) Linux Ubuntu Server virtual machine.
  - Virtual Machine Administrator Login Role assignments are assigned to the Information Technology Group at the VM Level.

**Steps**

Create an Azure Logic App. Within the app, create 4 triggers.

![image](https://github.com/arana2/Onboard-Automator/assets/38359810/7cc0a2ef-6f9e-403d-8fe4-cb7722bb6b68)

Trigger #1 - When an HTTP request is received.
- This trigger is used to collect the new employee information through HTTP even such as Sharepoint or an incoming email.
<img width="756" alt="image" src="https://github.com/arana2/Onboard-Automator/assets/38359810/cd3e3a81-43b9-40c8-9782-7d83008f5b38">

Trigger #2 - Create User
- This trigger will use the information from Trigger #1 to create a new user.
<img width="520" alt="image" src="https://github.com/arana2/Onboard-Automator/assets/38359810/1f6049e0-d20c-471c-8320-a9e0fba7bb27">

Trigger #3 - Add user to group
- This trigger will add the user to the Information Technology group. Note, this group was previously created.
<img width="705" alt="image" src="https://github.com/arana2/Onboard-Automator/assets/38359810/3281bb4b-36e8-4100-a6ba-0658b69fa67f">

Trigger #4 - Send an email (V2)
- This trigger will be used to send an automated email to the new employee which contains their username.
<img width="658" alt="image" src="https://github.com/arana2/Onboard-Automator/assets/38359810/5e93eaa7-d4ad-4084-831e-90c6863c59aa">

**Testing**

1. Run the Logic App with sample payload.

<img width="436" alt="image" src="https://github.com/arana2/Onboard-Automator/assets/38359810/9c71bd05-f590-4b18-8b38-0ede5f60e188">

2. Confirm new employee email has been received.

3. Confirm the user has been created and added to the Information Technology group.

<img width="762" alt="image" src="https://github.com/arana2/Onboard-Automator/assets/38359810/af07defd-cc3e-4488-8a3f-a52c9ea31118">

4. Confirm the new user has access to the virtual machine resources.
<img width="1485" alt="image" src="https://github.com/arana2/Onboard-Automator/assets/38359810/b4531ebb-5fa1-42ea-94ea-db4f788926ad">

**Conclusion**
This project was enjoyable and provided a learning experience in Azure's Manage Identities and Compliance domain. It did not involve any coding apart from understanding the JSON format.

Reference:
https://github.com/madebygps/projects/blob/main/az-104/onboarder.md

**Azure Logic Apps **is a cloud service provided by Microsoft Azure, enabling users to build and execute workflows for automating business processes and integrating diverse services and applications. A Logic App workflow consists of a sequence of steps designed to automate a specific task or process. In this instance, I have developed a Logic App workflow. Initially, I select a trigger, which could be an event such as a new employee record in a SharePoint list or an incoming email to a designated mailbox. This allows me to test and demonstrate the functionality of the automation. Once the trigger event occurs, the Logic App workflow is activated.
