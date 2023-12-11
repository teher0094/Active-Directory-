# Active Directory User and Access Management Project

## Project Overview
This project showcases my ability to manage an Active Directory (AD) environment, specifically focusing on creating and managing users, organizational units (OUs), and groups, and configuring shared folder access permissions.

## Objectives
- **User Creation:** Establish a variety of user accounts in AD.
- **OU Structuring:** Organize users into appropriate Organizational Units.
- **Group Management:** Create and manage groups for different access levels.
- **Shared Folder Access:** Set up shared folders and configure access permissions based on group membership.

## Technologies Used
- Microsoft Active Directory
- Microsoft Azure
- Windows 10 Pro
- Group Policy Management
- Group Policy Editor

## Organizational Units (OUs) and Groups Structuring
- In my Active Directory project, I created a structured environment for a hypothetical company named Americorp. This conceptual project was designed to demonstrate my understanding of AD's hierarchical organization.
- Americorp, envisioned as a small-scale enterprise with 11 employees, includes four key departments: Admins, Human Resources, Sales, and IT. To mimic a realistic corporate structure in AD, I crafted OUs corresponding to each of these departments.
- My approach was to create a clear and manageable framework, starting from the Americorp root OU and branching out into department-specific OUs. Within each departmental OU, I established a representative group: 'Hiring Team' for Human Resources, 'Sales Group' for Sales, and 'Helpdesk' for IT.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/9e3d0f12-1f26-40ea-955f-9ed1672bc478)

## User Creation

### Creating Users and Managing User Properties  
- I utilized ADUC to create 2 Domain Admins and 9 Domain Users. I created two Domain Admins to simulate a real-world scenario where multiple administrators are needed for redundancy and workload distribution.
- The other nine users, designated as Domain Users, were organized into three groups for effective management and to represent different departmental roles within the organization.
- Each user was assigned to a specific Organizational Unit (OU) group. Although the assignments in this project were arbitrary, they were designed to mimic a typical workplace setting where users are categorized based on their job functions.
- This part of the project helped me understand the importance of structured user placement in AD for both security and organizational efficiency.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/4dd2f0b6-c80d-4bba-a94a-1b467ebc12f1)

- The image above showcases the IT OU, including the 'Helpdesk' group and its members. This visual representation highlights the hierarchical arrangement of users and how ADUC facilitates easy navigation and management of these entities.
- The process of creating users and groups was straightforward, using ADUC's 'Create new user' and 'Create new group' features. This simplicity is one of the strengths of ADUC, allowing for efficient administration even in more complex environments.
- By grouping users, I laid the groundwork for future policy applications. For example, any security policies or access permissions applied to the 'Helpdesk' group would automatically cascade to its members, thereby simplifying permissions management significantly.
- Security best practices were a key focus in user account creation. I set up accounts with temporary passwords and enabled the option for users to change their passwords upon their next login. This approach ensures individual password security, as the initial creator of the account doesn't know the user's chosen password.

## Shared Folder Access Configuration

### Creating Shared Folders and Mapping Share Drives
- In my Active Directory setup, which comprises a Domain Controller and a Client, I took strategic steps to manage shared resources effectively:
- I chose the D: drive of the Client VM to host the 'Share Drive', intentionally separating it from the critical domain services on the DC. This decision not only minimized security risks but also ensured that the DC's performance remains dedicated to core domain functions.
- Within the 'Share Drive', I created four subfolders – 'All Access', 'IT Only', 'HR Only', and 'Sales Only'. Each folder was configured with different access levels to ensure department-specific data security. The NTFS and share permissions were set to reflect these access requirements.

 ![image](https://github.com/teher0094/Active-Directory-/assets/153027290/f29a2222-3059-4768-aefe-0160d4c5e102)


- The All Access folder was designed for company-wide collaboration, where every domain user has read and write permissions, making it easy to share information across the entire organization.
- For the departmental folders ('IT Only', 'HR Only', and 'Sales Only'), I used Group Policy Management and the Group Policy Editor to create new GPOs. These GPOs were linked to each department's OU, ensuring that shared drives are automatically mapped for users based on their group memberships.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/44051984-2044-416b-8d28-9e621fcde443)


![image](https://github.com/teher0094/Active-Directory-/assets/153027290/7d3e5f43-d272-4f9c-85f1-45ebde97e77d)

- Access to these folders is exclusively reserved for members of corresponding groups, enhancing data security and privacy. For instance, 'James Kirk', as a member of the 'Hiring Team' group, can access the 'HR Only' share drive, aligning access rights with organizational roles.
- When 'James Kirk' attempts to access a restricted folder like 'IT Only', an error message communicates the lack of permission, reinforcing security measures and user awareness.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/16b1c113-8759-4adb-85be-dc7ca6f82fd5)


### Configuring Access Permissions
- In the configuration of the Share Drive, I initially set it up with general access permissions for all domain users, allowing every user in the domain read and write capabilities. However, to tailor the access for specific departments, I modified these permissions for the subfolders.
- Each subfolder was initially inheriting these broad permissions from the Share Drive. To create a more controlled access environment, I had to remove this inheritance. I achieved this by navigating to the 'Security' tab in the 'Properties' of each subfolder. Here, I removed the 'Domain Users' group from the access list, effectively revoking their inherited permissions.
- Afterward, I added the appropriate departmental groups to each subfolder. For example, the 'HR Only' folder was assigned exclusively to the 'HR' group. This action ensured that only the members of each specific group had access to their relevant folders, aligning access rights with departmental needs and enhancing overall data security.

## Challenges and Solutions
- Setting up and managing an Active Directory environment was a significant learning curve for me, given that many of these processes were new territory. Each tool in AD, I realized, has its own depth and versatility, applicable in a wide range of scenarios.
- One particular challenge I faced was understanding the intricacies of Group Policy Management. It initially seemed daunting with its multitude of settings and options. To navigate through this, I actively sought out resources, diving into technical forums, and Microsoft's own documentation. These platforms provided valuable insights and practical tips, helping me demystify the complex aspects of AD.
- Additionally, watching tutorials from seasoned IT professionals proved immensely beneficial. Not only did they offer step-by-step guidance, but they also showcased best practices in real-world contexts. Applying these learnings, I was able to effectively set up group policies and fine-tune access controls in my project.

## Conclusion
- Although I am Comptia A+ certified, this project helped me put into practice what I've learned.
- There was alot of theory and abstract learning needed to pass the Comptia A+ exams but doing these projects gives me tangible experience that I can use during employment.
- Managing my own AD environment has helped me to better understand the security and structure of an organization.  


