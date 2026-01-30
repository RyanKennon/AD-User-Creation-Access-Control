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

---

### 1) Environment Setup

- **Platform:** Microsoft Azure
- **Domain Controller:** Windows Server (Azure VM)
- **Client VM:** Windows 10 (Azure VM)
- [Setup an Active Directory Domain](https://github.com/RyanKennon/AD-Domain-Setup/blob/main/README.md)

### ADD PICTURE HERE

---

### 2) Create Organizational Units

1. Open the **Server Manager** on the **Domain Controller**
2. Select **Tools** then **Active Directory Users and Computers**

### ADD PICTURE HERE

3. Right click the **domain**
4. Open the **New** submenu
5. Then select **Organizational Unit**

### ADD PICTURE HERE

6. Create 3 Organizational Units called: Employees, Admins, and Groups

### ADD PICTURE HERE

---

### 3) Create a User

1. Right click the **Employees** folder
2. Open the **New** submenu
3. Then select **User**

### ADD PICTURE HERE

4. Enter the User's information

---

### 4) Create Security Groups

1. Open the **Groups** folder
2. Open the **New** submenu
3. Then select **Group**
4. Name the Group: Human Resources

### ADD PICTURE HERE

5. Double click the **Human Resources** security group
6. Select **Members** then select **Add**
7. Enter the name of the user then **Check Names**
8. Confirm the changes

### ADD PICTURE HERE

---

### 5) Assign Folder Permissions

1. On the C drive create 3 folders named: HR-ReadWrite, HR-ReadOnly, and AdminsOnly

### ADD PICTURE HERE

2. Open the **Properties** for the folder called **HR-ReadWrite**
3. Then select **Sharing** then **Share**

### ADD PICTURE HERE

4. Then enter **Human Resources** in the box then select **Add**

### ADD PICTURE HERE

5. Then click the **dropdown arrow** and select **Read/Write**
6. Confirm the changes

### ADD PICTURE HERE

7. Do the same for the **HR-ReadOnly** folder except give it **Read** priveleges only.

### ADD PICTURE HERE

8. For the **AdminsOnly** folder, enter **Domain Admins** in the box before hitting **Add**
9. Select **Read/Write** priveleges for the **Domain Admins**

### ADD PICTURE HERE

---

### 6) Attempt to Access the Folders

1. **Log into the client VM** using the **credentials of the user** created earlier
2. Open the **File Explorer**
3. On the **Quick Access** bar search **\\<DC name>**

### ADD PICTURE HERE

4. Attempt to access the **HR-ReadWrite** folder and create a new file inside

### ADD PICTURE HERE

5. Attempt to access the **HR-ReadOnly** folder and attempt to create a new file inside

### ADD PICTURE HERE

6. Attempt to access the **NoAccess** folder

### ADD PICTURE HERE

---

### 7) Upgrade User to Domain Admin

1. Go back to **Active Directory Users & Computers** on the **Domain Controller**
2. Right click the user and select **Properties**
3. Select **Member Of** then **Add**
4. Type **Domain Admins**
5. Then **Check Names**
6. Confirm the changes

### ADD PICTURE HERE

---

### 9) Verify Admin Access

1. Log back in to the **client VM** using the **user's credentials**
2. Search **\\<DC name>** in the **Quick Access** bar again
3. Attempt to open the **AdminsOnly** folder and attempt to create a new file inside

### ADD PICTURE HERE

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
