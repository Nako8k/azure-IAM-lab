## Login & Setup

```bash
az login
az account show
```

<h2>Create Users</h2>

```bash
az ad user create --display-name "James Admin" --user-principal-name james.admin@cassidynakogmail.onmicrosoft.com --password "TempP@ss123!" --force-change-password-next-sign-in

az ad user create --display-name "Jane Admin" --user-principal-name jane.admin@cassidynakogmail.onmicrosoft.com --password "TempP@ss123!" --force-change-password-next-sign-in

az ad user create --display-name "Liam Hems" --user-principal-name liam.user@cassidynakogmail.onmicrosoft.com --password "TempP@ss123!" --force-change-password-next-sign-in

az ad user create --display-name "Tim Shayn" --user-principal-name tim.user@cassidynakogmail.onmicrosoft.com --password "TempP@ss123!" --force-change-password-next-sign-in

az ad user create --display-name "Mike Admin" --user-principal-name mike.admin@cassidynakogmail.onmicrosoft.com --password "TempP@ss123!" --force-change-password-next-sign-in
```

<h2>Verify Users</h2>

```bash
az ad user list --output table
```

<h2>Create Security Groups</h2>

```bash
az ad group create --display-name "AZ-Admin" --mail-nickname "AZ-Admin"
az ad group create --display-name "AZ-developers" --mail-nickname "AZ-developers"
az ad group create --display-name "AZ-readers" --mail-nickname "AZ-readers"
```

<h2>Add Members to Groups</h2>

```bash
az ad group member add --group "AZ-Admin" --member-id <user-object-id>
az ad group member add --group "AZ-developers" --member-id <user-object-id>
az ad group member add --group "AZ-readers" --member-id <user-object-id>
```

<h2>Verify Role Assignments</h2>

```bash
az role assignment list --all --output table
```
