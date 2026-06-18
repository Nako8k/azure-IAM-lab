# Azure IAM Lab - Identity & Access Management
> **Disclaimer:** All Azure resources created in this lab were deleted after completion. No services were left running. This lab was built purely for learning and documentation purposes.

---

<h2>Description</h2>
This lab focuses on Azure Entra ID and Access Management setup.

---

## What I covered in this Lab

- Creating users both manually and via Azure CLI
- Organizing users into proper security groups
- Assigning built-in RBAC roles across multiple scopes including subscription, resource group, and resource level

## Future planned objectives to cover

-  A Conditional Access policy requiring MFA requires a Premium 1 license. In this lab I am using a Free license
---

## Lab Structure 

```
azure-IAM-lab/
├── ReadMe.md
├── comands-reference.md
└── screenshots/
    ├── part1-User-accounts/
    ├── part2-security-groups/
    ├── part3-resource-group/
    ├── part4-Admin-roles/
    ├── part5-user-access/
    └── part6-role-assignments/
```
---

## Part 1 — User Accounts

I created 9 users in Microsoft Azure, 4 in the `CLI` and 5 via the `Entra Portal`

**Steps:**
1. I Navigated to **Entra ID** → **User** → **+ New User** → **+ Create**
2. I Created 5 users manually in Microsoft Entra ID
3. Then navigated to the **CLI** tab to create 4 additional users
<br />

<img src="https://imgur.com/7YWooq2.png" height="80%" width="80%" alt="Manual User Creation"/>
<br />
<img src="https://imgur.com/3fhJbE0.png" height="80%" width="80%" alt="CLI User Creation"/>
<br />
<img src="https://imgur.com/QenN0lX.png" height="80%" width="80%" alt="CLI User Creation"/>

---

## Part 2 — security groups (AZ-Admin, AZ-developers, AZ-readers)

I created three security groups to demonstrate how different permissions and roles can be assigned and managed within Azure.

**Steps:** 
1. Created the security groups via  **Entra ID** → **+ New Groups** → **+ Create**
2. I then assinded the users created inside `Entra ID` to their proper groups 

| Security groups | Role | Method 
|---|---|---|
| `AZ-Admin` | Admin | Portal |
| `AZ-Developers` | Developers | Portal |
| `AZ-Readers` | Readers | Portal |
<br />

<img src="https://imgur.com/NxrnOVo.png" height="80%" width="80%" alt="Security Group Creation"/>
<br />
<img src="https://imgur.com/B1wjd2L.png" height="80%" width="80%" alt="Group Member Assignment"/>
<br />
<img src="https://imgur.com/plj3g5p.png" height="80%" width="80%" alt="Group Member Assignment"/>
<br />
<img src="https://imgur.com/aL2CBxS.png" height="80%" width="80%" alt="Group Member Assignment"/>
<br />

---

## Part 3 — Resource Group

I created a resource group named `Az-Rg1-Dev` and set the region to **New Zealand North**.

**Steps:**
1. Navigate to **Resource groups** → **+ Create**
2. Name: `Az-Rg1-Dev` | Region: `New Zealand North`
3. Click **Review + create** → **Create**

---

## Part 4 — Admin Roles 

I assigned the **Owner** role to the **AZ-Admin** group at the **subscription scope**, 
as they serve as the primary administrators of the tenant and my lab.

<img src="https://imgur.com/bDO2HDY.png" height="80%" width="80%" alt="Owner Role Assignment"/>
<br />

---

## Part 5 — User Access 

Assigned User Access Administrator to James Admin and Jane Admin at subscription scope

<img src="https://imgur.com/e656X6l.png" height="80%" width="80%" alt="User Access Administrator Assignment"/>
<br />

---

## Part 6 - Role Assignements

**Steps:**
1. I assigned Contributor role to AZ-developers at the resource group scope (Az-Rg1-Dev)
2. Assign Reader role to AZ-readers at resource scope (raraunga1)
3. Confirm all role assignments via Access Control (IAM)

<img src="https://imgur.com/nojAMnL.png" height="80%" width="80%" alt="Contributor Role Assignment"/>
<br />
<img src="https://imgur.com/RqMFqvY.png" height="80%" width="80%" alt="Reader Role Assignment"/>
<br />
<img src="https://imgur.com/z1YrxWc.png" height="80%" width="80%" alt="Role Assignment Confirmation"/>

--- 
  
## Key Takeaways

- Demonstrated the fundamentals — of Identity and Access Management inside Microsoft Azure 
- Users were successfully created — both manually and through the Azure CLI 
- Organised users into proper security groups  
- Granted appropriate levels of access — through RBAC roles 
- Applied the principle of least privilege throughout — via assigning roles to groups rather than individuals

---
<h2>Lessons Learned</h2>

- <b>Understanding of Scope</b> — Creating this lab helped me understand the scope of different systems, access levels, etc.
Knowing the difference between access at the subscription level and access at the resource level makes all the difference,
and is something that should be considered carefully.
<br /><br />
- <b>Groups over individuals</b> — Providing privileges for different groups made tracking who had access to what much easier,
especially when deciding whether to remove a user from a group or move them to another.
This helped ensure that permissions were properly removed and reassigned when group memberships changed.
<br /><br />
- <b>Least privilege in practice</b> — The principle of least privilege is to grant only the minimum level of access required to complete a task.
I made sure that access and privileges were properly assigned to the appropriate users and groups to ensure compliance with this principle.
<br /><br />
- <b>CLI vs Portal</b> — I had learned that creating users through the CLI is significantly faster 
for bulk operations but requires careful attention to formatting. The Portal is more forgiving but slower compared to the CLI,
personally understanding both gave me a good perspictive on which is good for what operation.

---

*Lab completed by [@Nako8k](https://github.com/Nako8k)*
