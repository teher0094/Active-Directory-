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
- In my Active Directory project, I created a structured environment for a hypothetical company named Americorp.
- This conceptual project was designed to demonstrate my understanding of AD's hierarchical organization.
- Americorp, envisioned as a small-scale enterprise with 11 employees, includes four key departments: Admins, Human Resources, Sales, and IT.
- To mimic a realistic corporate structure in AD, I crafted OUs corresponding to each of these departments.
- My approach was to create a clear and manageable framework, starting from the Americorp root OU and branching out into department-specific OUs.
- Within each departmental OU, I established a representative group: 'Hiring Team' for Human Resources, 'Sales Group' for Sales, and 'Helpdesk' for IT.

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
- By adding users to a specific group, any future policies that applied to that group would apply to the user as well, making user permissions simplier to manage.  
- User accounts were created with a temporary password and the option for the users to change their password at the next log in was left checked.
- This is done so that the users will have unique passwords that the user creator would not know.

## Shared Folder Access Configuration

### Creating Shared Folders and Mapping Share Drives
- My Active Directory consists of a Domain Controller and a Client.
- I created the Share Folder on the "D:" of the Client VM, this way it will reduce the security concerns of my network and allow my DC to perform critical domain services only.
- The share folder is labled, "Share Drive", with 4 sub folders inside.
- Each of the folders will have a different level of access.
- The 4 subfolders are: All Access, IT Only, HR Only and Sales Only.

 ![image](https://github.com/teher0094/Active-Directory-/assets/153027290/f29a2222-3059-4768-aefe-0160d4c5e102)


- The All Access is a share folder that any domain user can access with read and write permissions.
- I was able to map the IT Only, HR Only and Sales Only folders as network share drives for their respective departments.
- Using Group Policy Management and Group Policy Editor, I created new GPOs linked to each OU so that the shared drives can be mapped to the correct groups and users in my AD.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/44051984-2044-416b-8d28-9e621fcde443)


![image](https://github.com/teher0094/Active-Directory-/assets/153027290/7d3e5f43-d272-4f9c-85f1-45ebde97e77d)

- Only members of their respective groups can access the corresponding share drive.
- The user, "James Kirk" is apart of the Hiring Team group, this is why they're able to see the HR Only Share drive and access it's contents.
- When James Kirk tries to access another folder such as the "IT Only" folder through the "Share Drive", they get an error message stating they do not have the permissions to do so.

![image](https://github.com/teher0094/Active-Directory-/assets/153027290/16b1c113-8759-4adb-85be-dc7ca6f82fd5)


### Configuring Access Permissions
- The Share Drive was create with access permissions for all domain users.
- All subfolders inherited these permissions but because I wanted certain share folders to become share drives for specific groups, I had to disinherit these permissions.
- I did this by going into the "Security" tab in the "Properties" of the Share Drive and removing the "Domain Users" from the access lists and then adding the appropriate group.

## Challenges and Solutions
- Because most of these processes and procedures are new to me, it was challenging setting up the AD environment and working within it.
- It seems each of these different AD tools holds a depth of services and can be used in many different circumstances.
- There's certainly much more for me to learn but I was able to research and find resolutions to any road blocks I've encountered during this project.
- Watching tutorials of IT professionals was a great aid in helping me to complete this. 

## Conclusion
- Although I am Comptia A+ certified, this project helped me put into practice what I've learned.
- There was alot of theory and abstract learning needed to pass the Comptia A+ exams but doing these projects gives me tangible experience that I can use during employment.
- Managing my own AD environment has helped me to better understand the security and structure of an organization.  


