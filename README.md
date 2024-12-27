# osticket-settings
Showing post-install configuration settings like groups and user settings.

## Logging into osTicket

Log into the virtual machine that has the osTicket webserver installed and configured on it, and go type `localhost/osTicket`. You should find yourself on a page that looks like this:

![1  osticket landing page](https://github.com/user-attachments/assets/d60b701f-c4de-47e6-9ad5-51d4f944fabb)

Click "Sign in" in the top right corner, then click "I'm an agent - sign in here", and use the credentials for the admin user you created when you installed osTicket to log into the admin tools for your helpdesk. You should land on a page that looks like this:

![2  admin landing page](https://github.com/user-attachments/assets/561672cb-649c-4203-8430-5557c617ec81)

There are lots of options that suddenly appear on your screen, but the most important distinction to recognize is the difference between the **Agent Panel** and the **Admin Panel**. Switch between them by clicking the name in the top right corner of the screen, next to your name. You'll always either be in one or the other, and the name not currently shown is the panel you're in. (Since you'd click the name of the other one to switch to it.)

- The Agent Panel is where tickets are worked and everything relating to active, closed, and archived tickets is stored. There are also knowledge bases for procedures, and ways for agents to sort tickets and use the panel as an organizational tool to prioritize tickets for optimal workflows.
- The Admin Panel is where system administration takes place. Here, you can create roles, groups, departments, and modify settings relating to how tickets are created and the classifications of problems that can be included in a ticket. Only users with administrator permissions may access the admin panel.

## Configuring [Roles](https://docs.osticket.com/en/latest/Admin/Agents/Roles.html)

In order to add, edit, or remove roles, go to the **Admin Panel -> Agents -> Roles**, to find a screen that looks like this.

![3  roles page](https://github.com/user-attachments/assets/3da4a04a-e353-49da-be3d-1b76ca2e3bd8)

For demonstration purposes, let's add a role called "Omniadmin" that has every permission, so we can demonstrate logging in on a different account and not lose any functionality. Click "Add New Role" to begin.

There are two main categories on the New Role page:

- **Definition**, which is where the role is named and notes are taken about what the role should do or a description of who should get the role, and
- **Permissions**, where abilities to modify, edit, create, delete, view, or any other action are selected for the role. Permissions are divided into three segments - Tickets, Tasks, and Knowledgebase. Permissions relating to each part of the helpdesk will be found in the corresponding menu.

![4  roles definition](https://github.com/user-attachments/assets/90063e41-5df4-491b-bae1-b1f31149fd92)

![5  permissions page](https://github.com/user-attachments/assets/840f4ae7-a7a3-4183-b02d-93d854103778)

We'll just check all the options for our Omniadmin, add the role, then create another role called "Support Agent" who will represent an entry-level worker who can work tickets and manage their own tasks, but cannot delete tickets or edit other agent's threads. At any time, you can go to the Roles page and click a role to view its permissions, definition, and internal notes. If you have the access, you can also edit existing roles.

![6  finished roles](https://github.com/user-attachments/assets/086bcc13-29c6-4333-b4c2-ab164427abb3)

## Configuring [Departments](https://docs.osticket.com/en/latest/Admin/Agents/Departments.html)

In osTicket, tickets are routed through departments before being assigned to users. In a business settings, deparments could be created and configured for every aspect of a business that would be interacting with the tickets. "Help Desk" could be a department, along with "Networking" and "Sysadmins", each playing a different role in the company and with different permissions based on the responsibilities for each one.

To get to the "Departments" page, go to **Admin Panel -> Agents -> Departments**. You should find a page that looks like this:

![7  departments page](https://github.com/user-attachments/assets/d7bfd87f-4d79-4022-ad46-d795338d0034)

Here you can view, edit, create, and manage departments. Let's get rid of the "Maintenance" department, and create a new department called "Admins" so that way we can practice multiple aspects of department management.

To delete "Maintenance", simply select it by ticking the box and then use the gear icon to select "Delete".

![8  deleting maintenance](https://github.com/user-attachments/assets/f75a6338-bbf9-4eea-876f-4b271d6edf73)

Next, click "Add New Department". Inside the creation menu, you will find two main sections:

- **Settings**, where the permissions and access of the department are managed. You can also create a department signature and manage email settings, and
- **Access**, where users are assigned to the department.

![9  new department settings](https://github.com/user-attachments/assets/ee3543cf-132b-4d8b-be87-618148204a1d)

![10  new department access](https://github.com/user-attachments/assets/60352a04-cb19-46e0-a4be-385ec3a22576)

"Admins" will be a top level department, public department with the default SLA (Service Level Agreement) and I will manage it. We don't have any users to add to it yet, so create it with zero users for now.

![11  finished departments](https://github.com/user-attachments/assets/68dfa10f-2264-4968-94a6-e6afee58fc53)

## Configuring [Teams](https://docs.osticket.com/en/latest/Admin/Agents/Teams.html)

Teams are a tool in osTicket that can be used to organize agents from different departments and assign them to projects or specific tickets. You can also assign team leaders who will receive notifications from team members. To navigate to the Teams menu, go to the **Admin Panel -> Agents -> Teams**.

![12  teams landing page](https://github.com/user-attachments/assets/790fa35f-f85e-4c81-8447-4b627faddcb9)

For our demonstration, let's create a team that deals specifically with distributing equipment to other members of the company. We'll call it "Equipment". Select "Add New Team" and look at the two menus that come up, "Team" and "Members".

- **Team** is where the team is named, a team leader is chosen, and notes are taken on the purpose of the team.
- **Members** is where other team members are assigned.

Create your team with zero members for now. Just like roles and departments, we can go back to this menu and click on a team at any time to edit and assign agents to them.

![13  finished teams](https://github.com/user-attachments/assets/580f792c-df33-4c53-a5e8-b7c5ccadff63)

## Configuring [Agents](https://docs.osticket.com/en/latest/Admin/Agents/Agents.html)

It's time to create some fake employees! In osTicket, "Agents" refers to employees who are working directly with the software and accessing and answering tickets. "Users" refers to end users who are submitting the tickets and needing help. For example, if Alice has trouble with her printer and sends a ticket that Bob eventually ends up working on, Alice is the "User", and Bob is the "Agent".
<!-- Yes, specifically Alice and Bob from the hypothetical cryptography examples. They stopped sending each other secret messages and got jobs. Maybe... -->

To create an Agent, go to the **Admin Panel -> Agents -> Agents** and you should land on a page that looks like this:

![14  agents landing page](https://github.com/user-attachments/assets/b4b46261-d9f8-43c9-ba23-fd455b55d57c)

You can view and sort agents by team and/or department, along with the creation and management options we've seen before in teams, departments, and roles. Click "Add New Agent" to hire someone to our helpdesk! Four categories of menu will appear.

- Account is where personal information, email, and username are assigned, along with some basics settings about how much access this person has.
- Access is where the agent is assigned to a department and given a role to play inside of it. Keep in mind that someone could be an Omniadmin in one department and a Support Agent in a different one.
- Permissions is where backend abilities are given across four categories: "Users", "Organizations", "Knowledgebase", and "Miscellanous". It's very similar to the permissions in our Roles creation.
- Teams is where you can assign the user to any number of teams when you create the account.

Let's create two employees, each with different responsibilities and levels of access to our system.

Jane - admin
John - support agent
