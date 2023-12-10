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

## Organizational Units (OUs) and Groups Structuring
- When creating OUs for the first time, I find that a high level approach is best because Active Directory is based on hierarchical structure.
- Starting from the company's name then moving onto the different departments in the company then the groups of each department and finally the users and resources in each group.
- In my project, I created a small company named Americorp which has 11 employees.
- Americorp has 4 departments: Admins, Human Resources, Sales and IT.
- I've created OUs based on each of those departments and a related group within each OU.
- For Human Resources, I created the group called Hiring Team, for the Sales OU, Sales Group, and IT OU, Helpdesk.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/9e3d0f12-1f26-40ea-955f-9ed1672bc478)

## User Creation

### Creating Users and Managing User Properties  
- The Active Directory Users and Computers is a great tool to used when it comes to managing the objects within an AD environment.
- I used ADUC to create 2 Domain Admins and the other 9 were Domain Users.
- The Domain Users were divided into groups of three.
- Each of those user were assigned to the different OU Groups.
- In this project, the user assignments were arbitrary but in the real world, I would have assign the users based on their hired positions.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/4dd2f0b6-c80d-4bba-a94a-1b467ebc12f1)

- In the picture above is an example of the IT OU, the group inside called Helpdesk and the members of that group.
- The users and groups were created using the "Create new user" and "Create new group" buttons. 
- User accounts were created with a temporary password and the option for the users to change their password at the next log in was left checked. 

## Shared Folder Access Configuration

### Creating Shared Folders
- My Active Directory consists of a Domain Controller and a Client.
- I created the Share Folder on the "D:" of the Client VM, this way it will reduce the security concerns of my network and allow my DC to perform critical domain services only.
- The share folder is labled, "Share Drive", with 4 sub folders inside.
- Each of the folders will have a different level of access.
- The 4 subfolders are: All Access, IT Only, HR Only and Sales Only.

 ![image](https://github.com/teher0094/Active-Directory-/assets/153027290/f29a2222-3059-4768-aefe-0160d4c5e102)


- The All Access is a share folder that any domain user can access with read and write permissions.
- The IT Only, HR Only and Sales Only were made into mapped network share drives for their respective departments.
- Only members of their respective groups can access the corresponding share drive.
- 

### Configuring Access Permissions
- Explain how you assigned folder permissions.
- Describe the process of linking folder access to specific OUs or groups.

## Challenges and Solutions

- Discuss any challenges faced during the project.
- Explain how you resolved these challenges.

## Conclusion

- Summarize the key outcomes of the project.
- Reflect on what this experience has taught you about managing an AD environment.


