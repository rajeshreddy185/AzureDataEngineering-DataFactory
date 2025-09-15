# **AZURE KEY VAULT**

Azure Key Vault is a cloud service provided by Microsoft Azure that offers a secure and centralized solution for managing and safeguarding sensitive information. 

It acts as a digital "vault" where you can store and control access to cryptographic keys, secrets.

- It has a fine-grained permission model (Azure RBAC or Access Policies).
- Ensures that only authorized users and applications can retrieve the stored objects.
- Examples: API keys, database connection strings, passwords, OAuth tokens, and SSH keys.

## 1. Create an Azure Key Vault

- Sign in to the Azure portal at portal.azure.com.
- In the top search bar, type "Key Vault" and select the service from the results.
- Click Create to start the creation process.
- On the "Create a key vault" page, fill in the following details:
  - Subscription: Select your Azure subscription.
  - Resource Group: Choose an existing resource group or create a new one.
  - Key Vault Name: Provide a globally unique name.
  - Region: Select a region.
  - In the "Permissions model" tab, it's recommended to select "Azure role-based access control" (Azure RBAC) as it provides a more granular and secure way to manage access than the older "Vault access policy" model.
  - Leave other settings as default for a basic setup. Click Review + create, and then Create.
    
<img width="900" alt="azurekeyvault" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2010.56.58%20PM.png" />

<img width="900" alt="azurekeyvault1" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2010.57.08%20PM.png" />

### 2. Assign Roles to the Key Vault

- After the Key Vault is deployed, you need to assign roles to users, groups, or applications to grant them permissions.
- Navigate to your newly created Key Vault resource.
- In the left-hand menu, select Access control (IAM). This is where you manage Azure RBAC roles.
- Click + Add and then Add role assignment.
- In the "Add role assignment" pane:
  - Role: Search for and select a built-in role. For Key Vault, common data plane roles include Key Vault Secrets Officer (for read/write access), Key Vault Secrets User (for read-only access), or Key Vault Administrator.
  - Members: Select the user, group, or service principal you want to assign the role to.
  - Click Review + assign, and then Review + assign again to finalize the role assignment.

<img width="900" alt="azurekeyvault2" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2010.58.38%20PM.png" />

<img width="900" alt="azurekeyvault3" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2010.59.00%20PM.png" />


### 3. Create a Secret Object in Azure Key Vault

- You can create a secret using the Azure portal or the Azure CLI.

Using the Azure Portal
- Navigate to your Key Vault: In the Azure portal, search for and select your Key Vault instance. If you don't have one, you'll need to create it first.
- Go to Secrets: In the left-hand navigation menu of the Key Vault, select Secrets under the "Objects" section.
- Generate/Import a Secret: Click the + Generate/Import button at the top.
- Configure the Secret:
  - Upload options: Choose Manual.
  - Name: Provide a unique, descriptive name for your secret (e.g., MyDatabaseConnection-string).
  - Value: Enter the actual sensitive value of the secret.
  - You can also set other properties like the content type, activation date, and expiration date.
- Create: Click Create to save the secret. It will now be listed in your Key Vault and can be referenced by your applications.

<img width="900" alt="azurekeyvault4" src="https://github.com/rajeshreddy185/polls/blob/main/mysite3-20210509T044718Z-001/mysite3/mysite3/Screenshot%202025-09-15%20at%2011.19.29%20PM.png" />



