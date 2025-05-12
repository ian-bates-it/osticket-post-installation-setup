# osTicket Post-installation Setup

---

<p align="center">
<img src="https://github.com/user-attachments/assets/767c4af0-9d0c-4ed8-8156-61a84a56a6ce" alt="Microsoft Active Directory Logo"/>
</p>

---




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




















