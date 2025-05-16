<p align="center">
<img src="https://github.com/user-attachments/assets/767c4af0-9d0c-4ed8-8156-61a84a56a6ce" alt="Microsoft Active Directory Logo"/>
</p>

# Chapter 2: osTicket Post-installation Setup

- In this chapter, we will log into the osTicket Admin Panel and create New Roles, Departments, Teams, Agents, Service Level Agreements (SLA), Users (end-users) and Help Topics.
- All of the settings we create in Chapter 2 will be used in the final [Chapter 3 of this series where we examine Tickets and the Ticket Lifecycle.](https://github.com/ian-bates-it/osticket-tickets-and-lifecycle) 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket Software version 1.15.8 
- Mcirosoft Visual C++ Redistributable (x86)
- IIS URL Rewrite Module 2
- PHP Manager For IIS 
- PHP version 7.3.8 
- MySQL version 5.5.62 
- HeidiSQL version 12.3.0.6589

<h2>Operating Systems Used </h2>

- Windows 10 Pro (21H2) 


<h2>High-Level Configuration Steps</h2>

- Part 1: [Log into the osTicket Admin Panel](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#log-into-osticket)
- Part 2: [View Roles and Add a New Role (`Super Admin`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-a-role)
  - Part 2A: [Set the Tickets Permissions for the New Role (`Super Admin`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#click-on-the-permissions-tab--tickets-permissions)
  - Part 2B: [Set the Tasks Permissions for the New Role (`Super Admin`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#click-on-the-permissions-tab--tasks-permissions)
  - Part 2C: [Set the Knowledgebase Permissions for the New Role (`Super Admin`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#click-on-the-permissions-tab--knowledgebase-permissions)
- Part 4: [View Departments and Add a New Department (`SysAdmins`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#osticket-departments)
  - Part 4A: [Set the Settings for the New Department (`SysAdmins`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#department-information--settings)
  - Part 4B: [Set the Access rights for the New Department (`SysAdmins`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#department-information--access-)   
- Part 5: [View Teams and Create a New Team (`Online Banking`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#osticket-teams)
  - Part 5A: [Set the Settings for the New Team (`Online Banking`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#new-team-settings)
- Part 6: [Confirm that Guest Accounts can create tickets](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#confirm-guest-accounts-can-create-tickets)
- Part 7: [Add a new Agent (`Jane Doe`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-a-new-agent)
  - Part 7A: [Repeat Part 7 and create a second agent (`John Doe`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-another-agent-john-doe)
- Part 8: [Add a New User (`Karen Doe`)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-a-new-user)
- Part 9: [Create a Service Level Agreement (SLA)](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#create-a-service-level-agreement-sla)
  - Part 9A: [Add New SLA called Sev-A](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-new-sla-plan-for-sev-a-sla)
  - Part 9B: [Add New SLA called Sev-B](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-new-sla-plan-for-sev-b-sla)
  - Part 9C: [Add New SLA called Sev-C](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-new-sla-plan-for-sev-c-sla)
- Part 10: [Create Help Topics](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#create-help-topics)
  - Part 10A: [Create New Help Topic: `Business Critical Outage`](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-new-help-topic-business-critical-outage)
  - Part 10B: [Create New Help Topic: `Personal Computer Issues`](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-a-second-help-topic-personal-computer-issues)
  - Part 10C: [Create New Help Topic: `Equipment Request`](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-a-third-help-topic-equipment-request-of-parent-topic-general-inquiry)
  - Part 10D: [Create New Help Topic: `Password Reset`](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-a-fourth-help-topic-password-reset-of-parent-topic-report-a-problem)
  - Part 10E: [Create New Catchall Help Topic: `Other`](https://github.com/ian-bates-it/osticket-post-installation-setup?tab=readme-ov-file#add-a-final-fifth-catchall-help-topic-other-of-parent-topic-general-inquiry)






<!--
## Prerequisites

- [Complete Chapter 1, Part 2 of the Active Directory Home Lab, Creating a Windows 10 Pro Virtual Machine (version 22H2) in Azure](https://github.com/ian-bates-it/Azure-Virtual-Machine-Setup?tab=readme-ov-file#part-2) 
  - _Or access to any Windows 10  or 11 operating system will be required for this particular series on osTicket._
-->


---
---
<br />

<h2>Log Into osTicket</h2>

- Log into the Admin osTicket account at this link: `http://localhost/osTicket/scp/login.php`
- Use the same Admin credentials we used [when setting up osTicket in the setup guide at this link](https://github.com/ian-bates-it/osticket-setup?tab=readme-ov-file#osticket-admin-user).

  <img src="https://github.com/user-attachments/assets/f9245c50-43d0-4aac-a286-d9cc4084c8d1" height="50%" width="50%" />



Roles - Grouping Permissions

- Roles give certain permissions to a group of people.



<h3>Admin Panel > Agents > Roles</h3>

- By default there are three different Roles.


  <img src="https://github.com/user-attachments/assets/6497668e-0701-40c6-a6c8-1129a4515c1e" height="50%" width="50%" />

<br />
<br />

---

<h3>View vs Expanded Access Roles</h3>

- View is Read Only.
- By contrast, the default `Expanded Access` role has many more permissions as shown here.
- 
you can assign roles to departments and teams

  <img src="https://github.com/user-attachments/assets/ce71e46d-ed1e-4139-9616-698398b1daf0" height="60%" width="60%" />




<br />
<br />

---

<h3>Add A Role</h3>

- In the `Agents > Roles` view, click on the `Add New Role` button as shown below.


  <img src="https://github.com/user-attachments/assets/ad0152d0-ba75-4e1a-9826-80c44d28fcdb" height="60%" width="60%" />


<br />
<br />



<h3>Name the New Role</h3>

- Type in the desired name for the new role.
- Here, I went with `Super Admin`.

  <img src="https://github.com/user-attachments/assets/7309212d-af3e-42fd-b605-5ebad9c458b3" height="50%" width="50%" />


<br />
<br />

---

<h3>Click on the Permissions Tab > Tickets Permissions</h3>

- Click the desired **ticket permissions** to be applied to this new role.
- Here, I selected all of the ticket permissions as shown below.

  <img src="https://github.com/user-attachments/assets/64dafab8-9fb2-4125-b92e-e839f33dbde8" height="60%" width="60%" />



<br />
<br />

---

<h3>Click on the Permissions Tab > Tasks Permissions</h3>

- Click the `Tasks` sub-menu and select the desired **tasks permissions** to be applied to this new role.
- Here, I seleted all of the Tasks permissions as shown below. 

  <img src="https://github.com/user-attachments/assets/78be40bb-be9b-4819-9062-76dcfecc8df3" height="60%" width="60%" />



<br />
<br />

---

<h3>Click on the Permissions Tab > Knowledgebase Permissions</h3>

-  Click the `Knowledgebase` sub-menu 
- Select the `Premade` Knowledgebase permissions if desired.
- Finally, click the `Add Role` button to complete the process of adding a new role as shown below.

  <img src="https://github.com/user-attachments/assets/179706db-dc29-4f6a-8e78-69fe052f6016" height="60%" width="60%" />



<br />
<br />

---

<h3>New Role Successfully Created</h3>

- Confirmation of our new role is provdied as shown below. 

  <img src="https://github.com/user-attachments/assets/ef5b65cf-8731-45c2-a5e9-e24777ba565d" height="60%" width="60%" />





<br />
<br />

---

<h2>osTicket Departments</h2>

- Departments are sectors like `Help Desk` vs `SysAdmins` vs `Networking`.
- Each department will have different visibility rights.


<br />
<br />

---

<h3>View Departments: Admin Panel > Agents > Departments</h3>

- To view `Departments` in the `Admin Panel:

1. Click on the `Agents` Tab.
2. Click on the `Departments` Tab as shown below.

  <img src="https://github.com/user-attachments/assets/94bfcb3f-d901-48f6-93de-c346471a8adc" height="60%" width="60%" />



<br />
<br />

---

<h3>Add A New Department</h3>

- In the Departments View, click the `Add New Department` button as shown below.

  <img src="https://github.com/user-attachments/assets/121dd992-95ea-4916-be77-5b517025e79a" height="60%" width="60%" />


<br />
<br />

---

<h3>Department Information > Settings</h3>

- The `Parent` field can be either `Top-Level` or a lower level. In this example, I will select `Top-Level Department`. 
- Add a name for the group. Here, I'll make a department named `SysAdmins`.
  
- We'll go with the default options for the other fields.
- Later, we will create an SLA, but for now we will leave that field with the `System Default`.

  <img src="https://github.com/user-attachments/assets/2609de1a-7e80-4d22-94df-2c32ad4ffa6d" height="60%" width="60%" />



<br />
<br />

---

<h3>Department Information > Access </h3>

- In the `Access` sub-tab, you would add an agent to the department we are creating.
- We will come back to this later after we create Agents to add to this department.

  <img src="https://github.com/user-attachments/assets/9a6d5cc9-b998-4307-a114-c8b2e8ac3c21" height="50%" width="50%" />


<br />
<br />

- Click the `Create Dept` button to create our example `SysAdmin` Department as shown below.

  <img src="https://github.com/user-attachments/assets/99f98500-fb86-4354-b1af-026b5e78ae99" height="50%" width="50%" />


<br />
<br />

---

<h3>New Department (`SysAdmins`) Successfully Created</h3>

- Confirmation that our new department `SysAdmins` was successfully created will look something like this:

  <img src="https://github.com/user-attachments/assets/b00eb0c8-009b-4031-a434-97763e597a76" height="50%" width="50%" />



<br />
<br />

---

<h2>osTicket Teams</h2>

- The purpose of Teams is to create a group of people who are all from DIFFERENT Departments.
- Example: Online Banking team may consist of people from the `SysAdmins` Department and `Customer Service` Department, etc.


<br />
<br />

---

<h3>Create A New Team</h3>

- In the `Agents > Teams` view, select the `Add New Team` button as shown below. 


  <img src="https://github.com/user-attachments/assets/e7059caf-4670-4e02-925b-e4ad9540a08d" height="90%" width="90%" />




<br />
<br />

---

<h3>New Team: Settings</h3>

1. Add a Team Name. In this example, I went with `Online Banking`
2. Click the `Create Team` button.


  <img src="https://github.com/user-attachments/assets/b77e68e6-eadf-4e69-ad35-360cc3205abb" height="60%" width="60%" />




<br />
<br />

---

<h3>Successfully Created New Team `Online Banking`</h3>

- Confirmation page:

    <img src="https://github.com/user-attachments/assets/cb1b1bbd-7f4e-41d6-8789-73ec256a3ecb" height="50%" width="50%" />






<br />
<br />

---

<h2>Confirm Guest Accounts Can Create Tickets</h2>

- For testing purposes, we will configure `osTicket` to allow anyone to create a ticket.
- Thus a user who is not registered can create a ticket. (guest accounts).




<br />
<br />

---

<h3>Navigate to Settings > Users > Authentication Settings</h3>

- Make sure the check-box next to `Registration Required` is not checked as shown below.

    <img src="https://github.com/user-attachments/assets/944fd39a-37cc-4cdb-aaf9-6bf5a5514c74" height="50%" width="50%" />






<br />
<br />

---

<h2>Add a New Agent</h2>

- An Agent is an individual registered user in osTicket.

  
<br />
<br />

---

<h3>Agents Tab > Add New Agent</h3>

- In the Agents Tab, select `Add New Agent`.

    <img src="https://github.com/user-attachments/assets/2dfff03f-8eeb-48ce-a33f-40d69b3a7e93" height="80%" width="80%" />

<br />
<br />

<h3>Create New Agent Account</h3>

1. Add Agent Name. Here I added `Jane Doe`
2. Add Email Address. Here I added jane@ianbates.com
3. Add Username. Here I added `jane`.
4. To set the password for the new agent, click the `Set Password` button.

    <img src="https://github.com/user-attachments/assets/c6e42de3-0ca1-410d-b6bd-b7f9006b21ec" height="60%" width="60%" />


<br />
<br />

5. In the pop-up window, uncheck the box for `Send the agent a password reset email`.

    <img src="https://github.com/user-attachments/assets/f77f4e0d-e415-4f4f-a00f-8d7b5c90cbcf" height="50%" width="50%" />

<br />
<br />

6. In the password fields, enter the desired password twice as shown below.
7. Click the `Set` button to complete this process.


    <img src="https://github.com/user-attachments/assets/d546ecd8-087f-4cbc-8f81-a056e3384e9f" height="50%" width="50%" />


<br />
<br />


8. Under the `Access` tab, select the **Primary Department** for the new Agent. 
9. Then select the **Role** for the new Agent.

    <img src="https://github.com/user-attachments/assets/e1304e9b-7d9f-4711-9c8c-d2dbb5edc2e4" height="50%" width="50%" />



<br />
<br />


10. Under the `Permissions` tab you can adjust the permissions for the new agent. Here we will just go with the default permissions as shown below.

    <img src="https://github.com/user-attachments/assets/e1c5b0ba-def6-49ff-bac1-bf19d954a21e" height="50%" width="50%" />


<br />
<br />


11. In the Teams tab, I used the drop down menu to add the new Agent to the Online Banking Team as shown below.
12. Finally, click the `Create` button to create our new Agent Jane Doe.


    <img src="https://github.com/user-attachments/assets/a54526fa-4ef7-4ff6-bbda-19459462c899" height="50%" width="50%" />



<br />
<br />


- Sucessfully created Jane Doe. Confirmation Message:


    <img src="https://github.com/user-attachments/assets/29676866-3159-4692-aa15-427bb18680f6" height="50%" width="50%" />


<br />
<br />



<h3>Add Another Agent: John Doe</h3>

- Following the 12 steps outlined above, I will repeat that process and create another Agent in osTicket with the following specifications

    - Name: `John Doe`
    - Email: `john@ianbates.com`
    - Username: `john`
    - Department: `Support`
    - Role: `Super Admin` (_This is a custom Role I created_)
    - Permissions: `Defaults`
    - Team: `None`
 


<br />
<br />

---


<h2>Add a New User</h2>

- The User is an end-user. Someone who might create a ticket, like a client.


<br />
<br />

---
<h3>Agent Panel > Users Tab > Add User</h3>

- Click on the `Agent Panel` link in the upper right-hand corner as shown below.


    <img src="https://github.com/user-attachments/assets/35769729-e2de-4711-86b3-6c482240df1e" height="50%" width="50%" />


<br />
<br />



---
<h3>Add New User</h3>

1. Within the Agent Panel, click on the `Users` tab.
2. Click on the `Add User` button.

    <img src="https://github.com/user-attachments/assets/4faaebf8-e52b-4b94-b53f-9256928ff16c" height="50%" width="50%" />

<br />
<br />

3. Add an email address for our User. In this case, I used `Karen@IanBates.com`.
4. Add Full Name for the User. In this case, I used `Karen Doe`.
5. Click the `Add User` button to complete this process.


    <img src="https://github.com/user-attachments/assets/22bf88fd-dd21-4992-8598-d6f861322962" height="50%" width="50%" />


<br />
<br />


<h3>New User Created Confirmation</h3>

- Our new user Karen Doe was created as shown below.


    <img src="https://github.com/user-attachments/assets/492a6f38-49c3-4721-b086-f27c8d64b6ef" height="80%" width="80%" />


<br />
<br />

---


<h2>Create a Service Level Agreement (SLA)</h2>

- SLA is basically how much time you have to do some specific task.
    - Responding to a ticket or completing a ticket.


- In this example, we will create three SLAs.

1. Sev-A - highest level of severity.
2. Sev-B - medium level of severity.
3. Sev-C - lowest level of severity. 


<br />
<br />


<h3>Admin Panel > Manage > SLA</h3>

- Click on the `Admin Panel` link in the top right corner to return to the **Admin Panel View** as shown below.


    <img src="https://github.com/user-attachments/assets/c7d24cc3-d46b-41d5-adf1-a6c3efec9261" height="50%" width="50%" />


<br />
<br />

1. In the `Admin Panel` view,  click on the `Manage` Tab.
2. Then, click on the `SLA` sub-menu. 
3. Finally, click on the `Add New SLA Plan` as shown below.

    <img src="https://github.com/user-attachments/assets/595dc2af-99ac-45c5-b198-ed0613ff54bd" height="70%" width="70%" />


<br />
<br />


<h3>Add New SLA Plan For Sev-A SLA</h3>

- SLA Name: `Sev-A`
- Grace Period: `1 Hour` (_This is for our most severe tickets_)
- Schedule: `24/7`
    - The default options here are 24 hours a day for 5 days a week,
    - 24 hours a day for 7 days a week,
    - Or Normal Business Hours.
        - Here, **I selected the 24 hours a day for 7 days a week Schedule**. 
- Go with the default options for everything else.
- Click `Add Plan` to create this SLA for `Sev-A`.

    <img src="https://github.com/user-attachments/assets/a9dc3960-aac7-4333-982a-4971a9eb1041" height="90%" width="90%" />



<br />
<br />


<h3>Add New SLA Plan For Sev-B SLA</h3>

- SLA Name: `Sev-B`
- Grace Period: `4 Hours` (_This is for a ticket of medium severity_)
- Schedule: `24/7`
    - The default options here are 24 hours a day for 5 days a week,
    - 24 hours a day for 7 days a week,
    - Or Normal Business Hours.
        - Here, I again **selected the 24 hours a day for 7 days a week Schedule**. 
- Go with the default options for everything else.
- Click `Add Plan` to create this SLA for `Sev-B`.

    <img src="https://github.com/user-attachments/assets/acd2396e-6b6d-4116-bf87-d7c3066cb1d6" height="90%" width="90%" />




<br />
<br />


<h3>Add New SLA Plan For Sev-C SLA</h3>

- SLA Name: `Sev-C`
- Grace Period: `8 Hours` (_This is for a ticket the lowest severity_)
- Schedule: `Monday - Friday 8am - 5pm with U.S. Holidays`
    - The default options here are 24 hours a day for 5 days a week,
    - 24 hours a day for 7 days a week,
    - Or Normal Business Hours.
        - Here, **I selected the Business Hours Options.**
- Go with the default options for everything else.
- Click `Add Plan` to create this SLA for `Sev-C`.


    <img src="https://github.com/user-attachments/assets/382cfd99-c8d8-4baa-a320-4e83442b6add" height="90%" width="90%" />
 


<br />
<br />


<h3>Summary of our Three New SLA's</h3>

- In the SLA menu, we can now see a summary of the three SLA's we created.

    <img src="https://github.com/user-attachments/assets/3adf2db8-a196-4f04-8d85-483ee8b25955" height="100%" width="100%" />





<br />
<br />

---


<h2>Create Help Topics</h2>

- `Help Topics` are predefined categories for issues that users may encounter.




<br />
<br />


<h3>Add New Help Topic: `Business Critical Outage`</h3>


1. From the `Admin Panel` view, click on the `Manage` Tab
2. Click on the `Help Topics` sub-menu.
3. Click the `Add New Help Topic` button as shown below.


    <img src="https://github.com/user-attachments/assets/b4a0ea39-859b-4702-bf4a-22b3201d6be8" height="50%" width="50%" />


<br />
<br />


4. Add Help Topic Name. Here I went with `Business Critical Outage`.
5. **Parent Topic**: I selected `Report a Problem`
  - Select the Parent Topic to which this Help Topic will belong. The Parent Topic will appear first in the listing with this Help Topic listed behind the parent.
6. Click the `Add Topic` button to complete this process.



    <img src="https://github.com/user-attachments/assets/9d6a6c3c-12ff-4ead-903a-49eb7db8dbfa" height="60%" width="60%" />





<br />
<br />


<h3>Add A Second Help Topic: `Personal Computer Issues`</h3>

- Repeating the six steps outlined above in the first help topic, I repeated that process to create a second help topic called `Personal Computer Issues` as shown below.


    <img src="https://github.com/user-attachments/assets/46048432-274b-4535-911d-45c9aa293028" height="60%" width="60%" />




<br />
<br />


<h3>Add A Third Help Topic: `Equipment Request` of Parent Topic `General Inquiry`</h3>


- Repeating the six steps outlined above in the first help topic, I repeated that process to create a third help topic called `Equipment Request` with a Parent Topic of `General Inquiry` as shown below.


    <img src="https://github.com/user-attachments/assets/27b8d825-babb-42ee-8adf-b0cc9e7f1ff1" height="60%" width="60%" />




<br />
<br />


<h3>Add A Fourth Help Topic: `Password Reset` of Parent Topic `Report a Problem`</h3>

- Repeating the six steps outlined above in the first help topic, I repeated that process to create a fourth help topic called `Password Reset` with a Parent Topic of  `Report a Problem as shown below.


    <img src="https://github.com/user-attachments/assets/ed97570d-1bed-4399-8831-9b00b3c23f4f" height="60%" width="60%" />




<br />
<br />


<h3>Add A Final Fifth Catchall Help Topic: `Other` of Parent Topic `General Inquiry`</h3>

- Repeating the six steps outlined above in the first help topic, I repeated that process to create a fifth help topic called `Other` with a Parent Topic of `General Inquiry` as shown below.

    <img src="https://github.com/user-attachments/assets/2a367128-56e7-4beb-b7ec-745fbaebb2e2" height="60%" width="60%" />


<br />
<br />

<h3>Summary of the Five New Help Topcics</h3>


- In the `Help Topics` view, we can see a summary of all five help topics that were added above.

![image](https://github.com/user-attachments/assets/27f6ed52-55ff-48bd-a0d5-638b8f4e6725)





<br />
<br />

<h3>This concludes the osTicket Post-Installation Setup</h3>


- To continue this series, see the next repo in this series [at this link here on osTicket Life Cycle.](https://github.com/ian-bates-it/osticket-tickets-and-lifecycle)


