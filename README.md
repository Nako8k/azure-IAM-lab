<h1>Azure IAM Lab - Identity & Access Management</h1>

<h2>Description</h2>
Project consists of a hands-on Azure Entra ID and Access Management setup built inside Microsoft Azure. The lab walks through creating users both manually and via Azure CLI, organizing them into security groups, and assigning built-in RBAC roles across multiple scopes including subscription, resource group, and resource level. A Conditional Access policy requiring MFA was also needed for admin users but will be skipped as it requires a Premium 1 license. In this lab I am using a Free license
<br />

<h2>Languages and Utilities Used</h2>

- <b>Azure CLI</b>
- <b>Microsoft Entra ID (Azure Active Directory)</b>
- <b>Azure Role-Based Access Control (RBAC)</b>

<h2>Environments Used</h2>

- <b>Microsoft Azure Portal</b>
- <b>Azure Free Subscription</b>
- <b>Windows 11</b>

<h2>Project Walk-Through:</h2>

<p align="center">
Create 5 users manually in Microsoft Entra ID: <br/><br />
<img src="https://imgur.com/7YWooq2.png" height="80%" width="80%" alt="Manual User Creation"/>
<br />
<br />
Create 4 additional users via BASH Azure CLI: <br/><br />
<img src="https://imgur.com/3fhJbE0.png" height="80%" width="80%" alt="CLI User Creation"/>
<br />
<br />
<img src="https://imgur.com/QenN0lX.png" height="80%" width="80%" alt="CLI User Creation"/>
<br />
<br />  
Create 3 security groups (AZ-Admin, AZ-developers, AZ-readers): <br/><br />
<img src="https://imgur.com/NxrnOVo.png" height="80%" width="80%" alt="Security Group Creation"/>
<br />
<br />
Assign members to each security group: <br/>
<img src="https://imgur.com/B1wjd2L.png" height="80%" width="80%" alt="Group Member Assignment"/>
<br /><br />
<img src="https://imgur.com/plj3g5p.png" height="80%" width="80%" alt="Group Member Assignment"/>
<br /><br />
<img src="https://imgur.com/aL2CBxS.png" height="80%" width="80%" alt="Group Member Assignment"/>
<br /><br />
<br />
Assign Owner role to AZ-Admin at subscription scope: <br/><br/>
<img src="https://imgur.com/bDO2HDY.png" height="80%" width="80%" alt="Owner Role Assignment"/>
<br />
<br />
Assign User Access Administrator to James Admin and Jane Admin at subscription scope: <br/><br/>
<img src="https://imgur.com/e656X6l.png" height="80%" width="80%" alt="User Access Administrator Assignment"/>
<br />
<br />
Assign Contributor role to AZ-developers at resource group scope (Az-Rg1-Dev): <br/><br/>
<img src="https://imgur.com/nojAMnL.png" height="80%" width="80%" alt="Contributor Role Assignment"/>
<br />
<br />
Assign Reader role to AZ-readers at resource scope (raraunga1): <br/><br/>
<img src="https://imgur.com/RqMFqvY.png" height="80%" width="80%" alt="Reader Role Assignment"/>
<br />
<br />
Confirm all role assignments via Access Control (IAM): <br/><br/>
<img src="https://imgur.com/z1YrxWc.png" height="80%" width="80%" alt="Role Assignment Confirmation"/>
<br />
<br />
Configure Conditional Access policy requiring MFA for AZ-Admin group: <br/>
<b>Note:</b> Conditional Access policy configuration requires an Azure AD Premium P1 license which was not available on this subscription. This step was documented as a planned objective but could not be completed in this environment.
<br />
<br />
Verify policy in Report-only mode: <br/>
<b>Note:</b> Unable to verify Conditional Access policy as the Premium P1 license required to configure and enforce this feature was not available on this subscription.
<br />
<br />
<h2>Key Takeaways</h2>
In this lab I demonstrated the fundamentals of Identity and Access Management inside Microsoft Azure. Users were successfully created both manually and through the Azure CLI, I had organised them into proper security groups, and granted appropriate levels of access through built-in RBAC roles across multiple scopes. The principle of least privilege was applied throughout by assigning roles to groups rather than individuals where possible. However Conditional Access with MFA enforcement remains a planned next step pending as I wait until an Azure Premium P1 license upgrade for my future labs and projects.
</p>
<h2>Lessons Learned</h2>

- <b>Understanding of Scope</b> — When I assigned a role at the subscription 
level it grants access to everything beneath it including all resource groups 
and resources. Understanding this hierarchy before assigning roles is critical 
to avoiding over-permissioning.
<br /><br />
- <b>Groups over individuals</b> — I learned that assigning RBAC roles to security groups 
rather than individual users makes access management significantly easier to 
maintain. Adding or removing a user from a group instantly updates their 
permissions without touching role assignments.
<br /><br />
- <b>Least privilege in practice</b> — I had learned that the difference between Owner and 
Contributor is the ability to manage access. Giving developers the role of Contributor 
instead of Owner means they can build and manage resources but cannot grant 
themselves or others elevated permissions or access.
<br /><br />
- <b>key security features</b> — Conditional Access with MFA 
enforcement requires Azure AD Premium P1. Because of this I was unable to document my experience, however this is still a real world lesson in how 
enterprise security are tiered behind licensing, understanding this before designing a security systems for an organisation will save time and 
provide insight.
<br /><br />
- <b>CLI vs Portal</b> — Creating users through the CLI is significantly faster 
for bulk operations but requires careful attention to formatting. The Portal 
is more forgiving but slower compared to the CLI, 
personally I have no preference and enjoyed using both system.
