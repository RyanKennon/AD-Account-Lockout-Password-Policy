<p align="center">
  <img src="https://github.com/user-attachments/assets/7b65e021-0e08-42ae-8da2-f57cd11aceb7" width="300" height="168" alt="image" />
</p>

# Active Directory: Account Lockout & Password Policy

# SAVE THIS PORTION FOR AN OVERVIEW

---

## Environments and Technologies Used

- Microsoft Azure
- Active Directory Users and Computers
- Group Policy Management
- Remote Desktop Protocol (RDP)

---

## Lab Objectives

- Prepare the Active Directory environment for testing password and account lockout behavior
- Simulate a user account lockout by intentionally entering incorrect login credentials
- Create and apply a custom Account Password Policy using Group Policy Management
- Unlock a locked-out user account and reset their password through Group Policy tools
- Verify that the updated password policy and account recovery steps function as intended
- Strengthen understanding of account security, password enforcement, and user recovery procedures within a Windows Server domain environment

---

## Step-by-Step Walkthrough

---

### 1) Environment Setup

- **Platform:** Microsoft Azure
- **Domain Controller:** Windows Server (Azure VM)
- **Client VM:** Windows 10 (Azure VM)
- [Setup an Active Directory Domain](https://github.com/RyanKennon/AD-Domain-Setup/blob/main/README.md)
- [Setup Users in Active Directory](https://github.com/RyanKennon/AD-User-Creation-Access-Control/blob/main/README.md)

<p align="center">
  <img width="1875" height="559" alt="Untitled Diagram-Page-1 drawio" src="https://github.com/user-attachments/assets/b3bd63ba-c0ba-48da-af1d-63ac35e005d9" />
</p>

---

### 2) Create an Account Password Policy

1. On the **Domain Controller** open the **Server Manager**
2. Select **Tools** then **Group Policy Management**

# ADD PICTURE HERE

3. Navigate through the **Forest** to the **Default Domain Policy**
4. Right click **Default Domain Policy** then choose **Edit**

# ADD PICTURE HERE

5. In the **Group Policy Management Editor** navigate through the **Policies** folder to the **Password Policy**

# ADD PICTURE HERE

6. Change the **Maximum Password Age** to **30 days**

# ADD PICTURE HERE

7. Change the **Minimum Password Length** to **12 characters**

# ADD PICTURE HERE

8. Open the **Account Lockout Policy**
9. Change the **Account Lockout Threshold** to **3 invalid login attempts**

# ADD PICTURE HERE

10. Change the **Account Lockout Duration** to **360 minutes**

# Add Picture Here

11. Go back to the **Group Policy Management** page
12. Right-click **Default Domain Policy**
13. Click **Enforce**

# ADD PICTURE HERE

---

### 3) Lockout the User Account

1. Attempt to log into the **client Virtual Machine** using an **incorrect password** four times

# ADD PICTURE HERE

---

### 4) Unlock User Account

1. Open **Active Directory Users and Computers**
2. Double click the **user**
3. Click **Account**
4. Check the box labeled **Unlock Account**
5. Apply the Changes

# ADD PICTURE HERE

---

### 5) Reset User's Password

1. Right click the **user**
2. Select **Reset Password**

# ADD PICTURE HERE

3. Enter the new password
4. Apply the Changes

# ADD PICTURE HERE

---

### 6) Verify Functionality

1. Attempt to log into the **client Virtual Machine** using the updated **user credentials**

# ADD PICTURE HERE
