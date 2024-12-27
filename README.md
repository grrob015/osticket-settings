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

Let's create two employees, each with different responsibilities and levels of access to our system. **Jane Doe** will be our Omniadmin and **John Doe** will be a new hire that works in Support. Once you've filled out the name, email, and username sections on the profile page, set a password. Since the emails we assign to our employees might not be real, untick the "Send the agent a password reset email" box and then untick the "Require password change at next login" box before setting a password. This allows for a permanent password that we can use indefinitely without getting locked out of our account because of email troubles. (💡 It's a really good idea to write down everyone's user and password on a Notepad file, as we'll have three accounts we're managing now and need to remember the credentials for.)

I created Jane by checking the "Administrator" box on the **Profile** section, giving her the Omniadmin role in both departments in the **Access** section, and ticking every unticked box in the **Permissions** section.
<!-- I felt that adding enough pictures here to show the options on every menu would clog the flow of the demonstration. Hopefully you're familiar enough with osTicket's UI by now to be able to do this. -->

I created John by adding him to the "Support" Department as a "Support Agent" in the **Access** section, unticking all boxes except for the ones that only allowed him to view things in the **Permissions** section (options 1 & 3 in "Miscellaneous"), and adding him to the Equipment team.

(⚠️ After you click "Create" at the bottom of the agent creation page, the page switches to **managing** the agent you just created (a way to tell is that the "Create" button has become a "Save Changes" button). Do NOT fill in the information for the next agent and then try to create it, you must go back to the agent page where you can view all your agents and then click "Add New Agent" again.)

## Configuring [End User](https://docs.osticket.com/en/latest/Agent/Users/User%20Directory.html) options

Now we can control and configure who gets to submit a ticket. In a real business scenario, you might have a whitelist of all the employees and import that into osTicket to create accounts for everyone so they can see what tickets they have open and view the progress of them at any time, but for this demonstration, we will allow guest tickets and not force a login. This is a very altruistic helpdesk.

Go to the **Admin Panel -> Settings -> Users** and you should find a page that looks like this:

![15  user settings landing page](https://github.com/user-attachments/assets/66829314-b217-414d-830b-a500e6b1e8de)

To allow guest tickets to be made, we will have the "Require registration and login to create tickets" box unticked, and I've also disabled session timeouts by changing the "User Session Timeout:" value to 0. Click "Save Changes" you're done!

## Configuring SLAs ([Service Level Agreements](https://docs.osticket.com/en/latest/Admin/Manage/SLA%20Plans.html))

SLAs (or Service Level Agreements) are the expected lengths of time that an administrator expects the tickets to be resolved within. It's a way to set ticket priorities based on the problem submitted and is a part of a helpdesk worker's job to work to be within. To manage SLAs within your osTicket help desk, go to the **Admin Panel -> Manage -> SLA**, and you should find yourself on a page that looks like this:

![16  sla landing page](https://github.com/user-attachments/assets/78c16f3c-2c22-46c5-a048-7ba8c46b657d)

Let's create a couple more SLAs to accompany the default for our examples. First, we'll make a high priority SLA for big problems that could affect the company very drastically. There are a few parts to an SLA, including:

- **Grace Period**: the amount of time that a ticket can go unanswered before first contact from a helpdesk employee to the ticket opener is made.
- **Schedule**: The time in which tickets are expected to be answered, commonly **24/7** or **24/5** (the entire week or only workdays, respectively.)
- **Transient**: Allows the SLA to be changed on a ticket if it needs to be escalated or de-escalated in priority.

![17  sla options](https://github.com/user-attachments/assets/31c20636-09f2-4494-a124-381aa8d40cc1)

Next, I'll make a low-priority SLA with a grace period of 6 hours on a 24/5 schedule that is transient. We now have three SLA levels to categorize tickets with for prioritization and contractual purposes! SLAs are very important for helpdesk employees to know aboout and abide by, as customer contact is a huge part of the job. (💡 The SLA settings here aren't the only ones that can show up in a working environment. It all depends on your employer, but an example of another stipulation that could appear in an SLA is emailing the customer every day with updates until the problem is fixed.)

## Configuring [Help Topics](https://docs.osticket.com/en/latest/Admin/Manage/Help%20Topic.html)


