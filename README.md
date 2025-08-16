<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Create Email Routing
- Configure Roles, Departments, Agents, and Teams
- Set up Service Level Agreements (SLAs)
- Configure Help Topics
- Create End-User(s)
- Test Ticket Creation

<h2>Access Information</h2>
  
- Help Desk Admin/Analyst Login URL: http://localhost/osTicket/scp/login.php
- End Users osTicket Support Center URL: http://localhost/osTicket/

<h2>Before You Begin</h2>

- Acknowledge Agent Panel vs Admin Panel

<p> 
<img width="1696" height="128" alt="image" src="https://github.com/user-attachments/assets/f92ea62e-5332-4950-9591-812e772ee0b7" />
<img width="1696" height="128" alt="image" src="https://github.com/user-attachments/assets/eb5542e8-88fd-4f98-8801-eff2bb963425" />
</p>
<p>

In osTicket, the Admin Panel is for system-wide configuration and management, while the Agent Panel is for managing tickets and interacting with users. Essentially, the Admin Panel is for managing the help desk itself, and the Agent Panel is for the agents who use it to provide support.
</p>
<br />

<h2>Configuration Steps</h2>
  
__Step 1__: Create Email Routing:
- Go to __Admin Panel__ → __Emails__ → __Settings__
- Enable email piping to convert emails to tickets
  
<br />

- (*Optional*) In the __Admin Panel__ navigate to __Settings__ → __Users__  
- Make sure *"Require registration & login to create tickets"* is unchecked to allow anyone to create tickets
<br />
<p>
  
__Step 2__: Configure Roles / Departments / Agents / Teams  

<img width="954" height="137" alt="image" src="https://github.com/user-attachments/assets/6d03934e-1a83-4f5c-be9a-68fc79c26183" />
</p>
<p>
  
**_Roles_**: Permissions granted to Agents per Department that they have access to. Each Role has a set of permissions that can be checked/unchecked for agents given that Role in association with a Department they have access to.
- Go to __Admin Panel__ → __Agents__ → __Roles__
- Click __+ Add New Role__
- Under the __Definition__ tab, create a Role such as:
> Admin  
> Supervisor  
> Support Agent
- Continue to the __Permissions__ tab → __Tickets__, select all relevant checkboxes to assign the appropriate permissions
- Do the same for the __Tasks__ & __Knowledgebase__ tabs
- Click __Add Role__ once the desired permissions are selected
  
<br />

**_Departments_**:  Tickets are routed through Departments in the help desk, which organize and direct requests to the appropriate staff members.
- Go to __Admin Panel__ → __Agents__ → __Departments__
- Click __+ Add New Department__
- In the __Parent__ dropdown menu select __Top Level Department__
- Create departments like: 
> IT Support  
> HR  
> Billing
- Configure the remaining optional fields, then navigate to the __Access__ tab to add relevant agents
  
<br />

**_Agents_**: Staff are given access to the help desk with the intent to respond and resolve the tickets. When adding an Agent to the help desk, they will need to be assigned to a Primary Department and given a Primary Role for the Tickets/Tasks routed to that department.
- Go to __Admin Panel__ → __Agents__ → __Agents__
- Click __+ Add New Agent__
- Under the __Accounts__ tab, create Agents as desired
- Proceed to the __Access__ tab to select __Departments__ & __Roles__
- Continue to __Permissions__ tab to assign the appropriate permissions
- Lastly, under the __Teams__ tab, assign the appropriate agents to their respective teams (*configured next*)

<br />

**_Teams_**: Allows pulling agents from different Departments and organizing them to handle a specific issue or user via a Help Topic or Ticket Filter.
- Go to __Admin Panel__ → __Agents__ → __Teams__
- Click __+ Add New Team__
- Under the __Teams__ tab, create a Team such as:
> Customer Care Team  
> VIP Support Team  
> Quality Assurance Team
- Proceed to the __Members__ tab to select Agents for current Team
- Click __Create Team__ to finish setup
</p>
<br />
<p>

__Step 3__: Configure SLAs (Service Level Agreements)

<img width="1793" height="673" alt="image" src="https://github.com/user-attachments/assets/8a624d0c-2bc1-4b5b-8972-2256b84ce21d" />
</p>
<p>

- Go to __Admin Panel__ → __Manage__ → __SLA__
- Click __+ Add SLA Plan__
- Create SLAs such as:
> Critical = 1 Hour  
> High Priority = 4 Hours  
> Normal = 8 Hours
- Configure __Grace Period__ & __Schedule__ for each Plan
- Click __+ Add Plan__ to finish setup
</p>
<br />
<p>

__Step 4__: Configure Help Topics:
- Go to __Admin Panel__ → __Manage__ → __Help Topics__
- Click __+ Add New Help Topic__
- Create Topics such as:
> Business Critical Outage  
> Personal Computer Issues  
> Equipment Request  
> Password Reset  
> Other
- Choose appropriate __Parent Topic__
- Click __+ Add Topic__ to finish setup
</p>
<br />
<p>
  
__Step 5__: Create End-User(s):
- Go to __Agent Panel__ → __Users__ → __User Directory__
- Click __+ Add User__
- Create custom User(s)
- Click __+ Add User__ to finish setup
</p>
<br />
<p>
  
__Step 6__: Test Ticket Creation:

<img width="1508" height="864" alt="image" src="https://github.com/user-attachments/assets/fceab931-6d43-4a04-a948-5431326ec3e8" />
</p>
<p>

- Create a test ticket via email or web form. Go to ➤ http://localhost/osTicket/
- Click __Open a New Ticket__
- Enter required contact details
- Choose a __Help Topic__ & make a brief description in the issue summary
- Click __Create Ticket__
- Confirm that the ticket appears in the admin panel
- Test response and escalation settings
</p>
<br />
<p>
  
Congratulations! Hopefully, the configuration has been completed without any errors.
</p>
<br />
