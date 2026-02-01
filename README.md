<p align="center">
  <img src="https://github.com/user-attachments/assets/7b65e021-0e08-42ae-8da2-f57cd11aceb7" width="300" height="168" alt="image" />
</p>

# Active Directory: User Creation & Access Control

This project focuses on **managing users, groups, and access control** within a **Windows Server Active Directory environment**. I created Organizational Units, provisioned a domain user, built security groups, and assigned folder permissions to enforce access restrictions. I then tested user access, elevated the user to Domain Admin, and verified the expanded permissions. This project demonstrates core skills in identity management, security group configuration, role-based access control, and administrative privilege management within a domain environment.

---

## Environments and Technologies Used

- Microsoft Azure
- Active Directory Users and Computers
- Remote Desktop Protocol (RDP)

---

## Lab Objectives

- Create and organize Active Directory structure using Organizational Units (OUs)
- Provision new user accounts within AD and apply appropriate account settings
- Configure folder and file system permissions to control user access
- Create test folders to validate permission assignments
- Verify user access to ensure permissions are applied correctly
- Create an administrative user with elevated privileges for management tasks
- Strengthen understanding of identity management and access control within a Windows Server domain

---

## Step-by-Step Walkthrough

### Lab Environment

- **Platform:** Microsoft Azure
- **Domain Controller:** Windows Server 2022 Datacenter
- **Client Machine:** Windows 10 Pro
- [Setup an Active Directory Domain](https://github.com/RyanKennon/AD-Domain-Setup/blob/main/README.md)

<p align="center">
  <img width="1875" height="559" alt="Untitled Diagram-Page-1 drawio" src="https://github.com/user-attachments/assets/b3bd63ba-c0ba-48da-af1d-63ac35e005d9" />
</p>

---

### 1) Create Organizational Units

1. Open the **Server Manager** on the **Domain Controller**
2. Select **Tools** then **Active Directory Users and Computers**

<p align="center">
  <img width="1920" height="759" alt="Untitled Diagram-Page-2 drawio" src="https://github.com/user-attachments/assets/e288e202-d97b-42fb-bb4e-5658a4e9fe63" />
</p>

3. Right click the **domain**
4. Open the **New** submenu
5. Then select **Organizational Unit**

<p align="center">
  <img width="755" height="531" alt="Untitled Diagram-Page-3 drawio" src="https://github.com/user-attachments/assets/8635d7b6-7680-4189-af90-ba22229373c2" />
</p>

6. Create 3 Organizational Units called: Employees, Admins, and Groups

<p align="center">
   <img width="754" height="530" alt="Untitled Diagram-Page-4 drawio" src="https://github.com/user-attachments/assets/df1a2b65-9fc2-439f-be2b-fbd7fc110984" />
</p>

---

### 2) Create a User

1. Right click the **Employees** folder
2. Open the **New** submenu
3. Then select **User**

<p align="center">
   <img width="755" height="549" alt="Untitled Diagram-Page-5 drawio" src="https://github.com/user-attachments/assets/62185a90-7adb-4ac9-964c-d1c3bcc2e80b" />
</p>

4. Enter the User's information

<p align="center">
   <img width="753" height="530" alt="Untitled Diagram-Page-6 drawio" src="https://github.com/user-attachments/assets/80ff677e-49a9-486f-b59a-6d47cf2066cb" />
</p>

---

### 3) Create Security Groups

1. Open the **Groups** folder
2. Open the **New** submenu
3. Then select **Group**

<p align="center">
   <img width="753" height="583" alt="Untitled Diagram-Page-21 drawio" src="https://github.com/user-attachments/assets/ecfd98c1-aad7-4f23-8f6a-71b54da52b74" />
</p>

4. Name the Group: Human Resources

<p align="center">
   <img width="754" height="530" alt="Untitled Diagram-Page-7 drawio" src="https://github.com/user-attachments/assets/7cdc7f08-cf95-444c-a7ac-472701c48984" />
</p>

5. Double click the **Human Resources** security group
6. Select **Members** then select **Add**
7. Enter the name of the user then **Check Names**
8. Apply the changes

<p align="center">
   <img width="1056" height="562" alt="Untitled Diagram-Page-8 drawio" src="https://github.com/user-attachments/assets/e40e3052-d247-4519-846b-0f13e256127f" />
</p>

---

### 4) Assign Folder Permissions

1. On the C drive create 3 folders named: HR-ReadWrite, HR-ReadOnly, and AdminsOnly

<p align="center">
   <img width="1125" height="633" alt="Untitled Diagram-Page-9 drawio" src="https://github.com/user-attachments/assets/bc89fd33-3fc2-48fc-b23d-d1200368f695" />
</p>

2. Open the **Properties** for the folder called **HR-ReadWrite**
3. Then select **Sharing** then **Share**

<p align="center">
   <img width="361" height="479" alt="Untitled Diagram-Page-10 drawio" src="https://github.com/user-attachments/assets/4997118c-879d-4ced-b7b3-a6c14a83a9fa" />
</p>

4. Then enter **Human Resources** in the box then select **Add**
5. Then click the **dropdown arrow** and select **Read/Write**
6. Confirm the changes

<p align="center">
   <img width="613" height="453" alt="Untitled Diagram-Page-11 drawio" src="https://github.com/user-attachments/assets/e5840ca3-0b27-43e3-a59f-b463ae41941a" />
</p>

7. Do the same for the **HR-ReadOnly** folder except give the Human Resources group **Read** priveleges only.

<p align="center">
   <img width="613" height="454" alt="Untitled Diagram-Page-12 drawio" src="https://github.com/user-attachments/assets/ce474a2d-0785-4e4e-9427-79ebdd7916bf" />
</p>

8. For the **AdminsOnly** folder, enter **Domain Admins** in the box before hitting **Add**
9. Select **Read/Write** priveleges for the **Domain Admins**
10. Apply the changes

<p align="center">
   <img width="613" height="453" alt="Untitled Diagram-Page-13 drawio" src="https://github.com/user-attachments/assets/5bb94385-5358-423c-b51f-3639bbb3d45e" />
</p>

---

### 5) Attempt to Access the Folders

1. **Log into the client VM** using the **credentials of the user** created earlier
2. Open the **File Explorer**
3. On the **Quick Access** bar search **`\\<DC name>`**

<p align="center">
   <img width="1124" height="633" alt="Untitled Diagram-Page-14 drawio" src="https://github.com/user-attachments/assets/81babfc6-144c-4ffa-b10c-225d43e2b849" />
</p>

4. Attempt to access the **HR-ReadWrite** folder and create a new file inside

<p align="center">
   <img width="1125" height="634" alt="Untitled Diagram-Page-15 drawio" src="https://github.com/user-attachments/assets/0ca74ee8-c7da-4869-a518-5c0010cd411d" />
</p>

5. Attempt to access the **HR-ReadOnly** folder and attempt to create a new file inside

<p align="center">
   <img width="1123" height="630" alt="Untitled Diagram-Page-16 drawio" src="https://github.com/user-attachments/assets/eb2b72df-bfb2-41a2-8823-0012887f433a" />
</p>

6. Attempt to access the **NoAccess** folder

<p align="center">
   <img width="1122" height="630" alt="Untitled Diagram-Page-17 drawio" src="https://github.com/user-attachments/assets/a09c2962-6d55-4b04-b54d-1fb3bd0ccdf4" />
</p>

---

### 6) Upgrade User to Domain Admin

1. Go back to **Active Directory Users & Computers** on the **Domain Controller**
2. Open the **Employees** folder then right click the user and select **Properties**

<p align="center">
   <img width="751" height="527" alt="Untitled Diagram-Page-20 drawio" src="https://github.com/user-attachments/assets/a7fb0f02-e418-43b2-96e2-0f246cdf8c54" />
</p>

3. Select **Member Of** then **Add**
4. Type **Domain Admin**
5. Then **Check Names**
6. Confirm the changes

<p align="center">
   <img width="653" height="536" alt="Untitled Diagram-Page-18 drawio" src="https://github.com/user-attachments/assets/ff9dd259-2533-40d6-bbcb-cbfba16e531b" />
</p>

---

### 7) Verify Admin Access

1. Log back in to the **client VM** using the **user's credentials**
2. Search **`\\<DC name>`** in the **Quick Access** bar again
3. Attempt to open the **AdminsOnly** folder and attempt to create a new file inside

<p align="center">
   <img width="1122" height="631" alt="Untitled Diagram-Page-19 drawio" src="https://github.com/user-attachments/assets/ad515c8e-0afe-4bd9-a4f6-4e9a72968a15" />
</p>

---

## Outcome

- Successfully created Organizational Units (OUs) to organize domain objects and establish a clear Active Directory structure  
- Created a standard domain user account and placed it in the appropriate OU  
- Built security groups to manage access control using role-based permissions  
- Assigned folder permissions to the newly created security groups to control access to shared resources  
- Tested folder access as the standard user and confirmed that permissions were enforced correctly  
- Upgraded the user to a Domain Admin account and verified elevated access rights  
- Confirmed that administrative privileges allowed full access to previously restricted folders  
- Demonstrated practical understanding of identity management, permission assignments, group-based access control, and administrative role escalation within a Windows Server domain environment

---

## Skills Demonstrated

- Organizing Active Directory environments using structured Organizational Units (OUs)
- Creating and managing standard domain user accounts
- Building and configuring security groups for role-based access control (RBAC)
- Assigning folder and file system permissions using groups rather than individual users
- Testing and verifying access permissions from the perspective of different user roles
- Modifying user privileges, including elevating a standard user to a Domain Admin
- Validating administrative access to restricted resources within the domain
- Strengthening practical understanding of identity management, access control, and Active Directory administration in a Windows Server environment
