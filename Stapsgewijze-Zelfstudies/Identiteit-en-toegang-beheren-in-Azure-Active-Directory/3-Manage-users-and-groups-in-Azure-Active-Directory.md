## 3 Manage users and groups in Azure Active Directory

[manage-users-and-groups-in-aad](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/)

Manage users and groups in Azure Active Directory
Learning objectives

|In this module, you will|
|---------------------------------------------------|
|Learn the difference between Azure AD and Windows Server Active Directory|
|Understand tenants, subscriptions, and users|
|[Create a new Azure Active Directory](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/2-create-aad)|
|Add users and groups to an Azure AD|
|Manage roles in an Azure AD|
|Learn how to create a hybrid identity solution with Azure AD Connect|


|1|3 min|[Introduction](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/1-introduction)|
|2|10 min|[What is Azure Active Directory?](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/2-create-aad)|
|3|8 min|[Create and manage users](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/3-users)|
|4|8 min|[Create and manage groups](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/4-groups)|
|5|10 min|[Use roles to control resource access](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/5-manage-aad-roles)|
|6|8 min|[Connect Active Directory to Azure AD with Azure AD Connect](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/|7-azure-ad-connect)|
|7|3 min|[Summary](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/7-summary)|


## What is Azure Active Directory?

 10 minutes

While they share a similar name, Azure AD is not a cloud version of Windows Server Active Directory. It's also not intended as a complete replacement for an on-premises Active Directory. Instead, if you are already using a Windows AD server, you can connect it to Azure AD to extend your directory into Azure. This approach allows users to use the same credentials to access local and cloud-based resources.

![tt](../../What-is-Azure-Active-Directory.png)

Azure AD can also be used independently of Windows AD. Smaller companies can use Azure AD as their only directory service, using it to control access to their applications and SaaS products such as Microsoft 365, Salesforce, and Dropbox.

Note

Keep in mind that this approach doesn't provide a completely centralized administrative model - for example, local Windows machines would authenticate using local credentials. But applications can be written to use Azure AD to provide authentication and authorization that can then be administered in a single place.
Directories, subscriptions, and users

Microsoft offers several cloud-based offerings today - all of which can use Azure AD to identify users and control access.

|cloud-based offerings today |
|----------------------------|
|Microsoft Azure|
|Microsoft 365|
|Microsoft Intune|
|Microsoft Dynamics 365|

When a company or organization signs up to use one of these offerings, they are assigned a default directory, which is an instance of Azure AD. This directory holds the users and groups that will have access to each of the services the company has signed up for. This default directory is sometimes referred to as a tenant. A tenant represents the organization and the default directory assigned to it.

Subscriptions in Azure are both a billing entity and a security boundary. Resources such as virtual machines, web sites, and databases are always associated to a single subscription. Each subscription also has a single account owner who is responsible for any charges incurred by resources in that subscription. If your organization wants the subscription to be billed to another account, you can transfer ownership of the subscription. A given subscription is also associated to a single Azure AD directory. Multiple subscriptions can trust the same directory, but a subscription can only trust one directory.

Users and groups can be added to multiple subscriptions - this allows the user to create, control, and access resources in the subscription. When you add a user to a subscription, the user must be known to the associated directory as shown in the following image.

Conceptual art showing users, directories, and subscriptions in Azure


![tt](../../pictures/multiple-subscriptions.png)

If you belong to multiple directories, you can switch the current directory you are working in through the Directory + subscription button in the Azure portal header.

![tt](../../pictures/directory_plus_subscription.png

Here you can also decide how the default directory is selected: last visited, or a specific directory. You can also set the default filter for displayed subscriptions. This is useful if you have access to several subscriptions but typically only work in a few of them.
Creating a new directory

An organization (tenant) always has one default Azure AD directory it's associated with, however owners can create additional directories to support development or testing purposes, or because they want to have separate directories to synchronize with their local Windows Server AD forests.

Important
[The steps to create a new directory are shown below](https://docs.microsoft.com/en-us/learn/modules/manage-users-and-groups-in-aad/2-create-aad), however unless you are an owner of your Azure account, this option won't be available to you. The Azure Sandbox doesn't allow you to create new Azure AD directories.


|step| the steps to create a new directory |
|------|------------------------------------------------------|
|1|Sign into the Azure portal .|

![tt](../../pictures/Sign-into-the-Azure-portal-https-porta-azure-com-home.png)


|step| the steps to create a new directory |
|------|------------------------------------------------------|
|2|Select Create a resource from the left sidebar, Identity from the Azure Marketplace, and then Azure Active Directory from the list.|


![tt](../../pictures/AZ_resource_Azure_Active_Directory_from_the_list.png)

````
Azure Active Directory is an Identity and Access Management as a service (IDaaS) solution that extends your on-premises directories into the cloud and provides single sign-on to Azure, Office 365 and thousands of cloud (SaaS) apps and access to web apps you run on-premises.
Built for ease of use, Azure Active Directory enables enterprise mobility and collaboration and delivers advanced identity protection through multi-factor authentication (MFA), security reports, audits, alerts and adaptive conditional access policies based on device health, user location and risk level.
````

![tt](../../pictures/Identity-and-Access-Management-as-a-service-IDaaS.png)


|step| the steps to create a new directory |
|------|------------------------------------------------------|
|3|Choose a name for the directory that will help distinguish it from your other directories. If the directory you're creating is to be used in production, choose a name for the directory that your users will recognize as the name of your organization. You can change the name later if you want.|



![tt](../../pictures/create_discipl_aad_00.png)
![tt](../../pictures/create_discipl_aad_01.png)
![tt](../../pictures/create_discipl_aad_02.png)
![tt](../../pictures/create_discipl_aad_03.png)
![tt](../../pictures/create_discipl_aad_04.png)





|step| the steps to create a new directory |
|------|------------------------------------------------------|
|4|Enter the domain name associated with it. The domain must not be known to Azure or you will get a validation error. The default domain name will always have the suffix .onmicrosoft.com. While this default domain cannot be changed, later you can add a custom domain owned by your organization so defined users can use a traditional company email such as john@contoso.com.|


|step| the steps to create a new directory |
|------|------------------------------------------------------|
|5|Select the country the directory should reside in. This will identify the region and data center where the Azure AD instance will live and it cannot be changed later.|


|step| the steps to create a new directory |
|------|------------------------------------------------------|
|6|Select Create to create the new directory. This will create a free tier directory where you can add users, create roles, register apps and devices, and control licenses.|


![tt](../../pictures/select_AAD_country.png)

Once the directory is created, you can navigate to the dashboard that lets you control all aspects of the directory.

![tt](../../pictures/dashboard-that-lets-you-control-all-aspects-of-the-directory.png)

## Check your knowledge

|1. An Azure subscription is a _______________.|
|-----------------------------------------------------|
|x billing entity and security boundary|
|container that holds users|
|monthly charge for Azure services|

|2.Which of the following best describes the relationship between a subscription and an Azure AD directory?|
|-----------------------------------------------------|
|An Azure AD directory has a 1:1 relationship with a subscription.|
|# An Azure AD directory can be associated with multiple subscriptions, but a subscription is always tied to a single directory.|
|An Azure AD directory is associated with a single subscription, but a subscription can trust multiple directories.|

|3. True or False, an organization can have more than one Azure AD directory.|
|-----------------------------------------------------|
|xTrue|
|False|


![tt](../../pictures/congratulations_aad.png



![tt](../../pictures/ADD_tenant.png)

![tt](../../pictures/ADD_tenant_00.png)

![tt](../../pictures/ADD_tenant_01.png)

![tt](../../pictures/ADD_tenant_02.png)

![tt](../../pictures/ADD_tenant_03.png)

![tt](../../pictures/ADD_tenant_04.png)

![tt](../../pictures/ADD_tenant_05.png)

![tt](../../pictures/ADD_tenant_06.png)

![tt](../../pictures/ADD_tenant_07.png)

![tt](../../pictures/ADD_tenant_08.png)

![tt](../../pictures/ADD_tenant_09.png)

![tt](../../pictures/ADD_tenant_10.png)

![tt](../../pictures/ADD_tenant_11.png)

![tt](../../pictures/ADD_tenant_12.png)

![tt](../../pictures/ADD_tenant_13.png)

![tt](../../pictures/ADD_tenant_14.png)

![tt](../../pictures/ADD_tenant_15.png)

![tt](../../pictures/ADD_tenant_16.png)

![tt](../../pictures/ADD_tenant_17.png)


Next unit: Create and manage users

## Create and manage users

    8 minutes

Every user who needs access to Azure resources needs an Azure user account. A user account contains all the information needed to authenticate the user during the sign-on process. Once authenticated, Azure AD builds an access token to authorize the user and determine what resources they can access and what they can do with those resources.

You use the Azure Active Directory dashboard in the Azure portal to work with user objects. Keep in mind that you can only work with a single directory at a time - but you can use the Directory + Subscription panel to switch directories. The dashboard also has a Switch directory button in the toolbar which makes it easy to switch to another available director


## Viewing users

To view the Azure AD users, select the Users entry under the Manage group - this will open the All Users view. Take a minute to access the portal and view your users. Notice the USER TYPE and SOURCE columns, as the following figure depicts.

Screenshot that depicts the All users pane, with the USER TYPE and SOURCE columns noted.


|way|Typically, Azure AD defines users in three ways:|
|-------------------|-------------------------------------------------------------------|
|Cloud identities -| These users exist only in Azure AD. Examples are administrator accounts and users that you manage yourself. Their source is Azure Active Directory or External Azure Active Directory if the user is defined in another Azure AD instance but needs access to subscription resources controlled by this directory. When these accounts are removed from the primary directory, they are deleted.
|  Directory-synchronized identities |- These users exist in an on-premises Active Directory. A synchronization activity that occurs via Azure AD Connect brings these users in to Azure. Their source is Windows Server AD.|
|Guest users -| These users exist outside Azure. Examples are accounts from other cloud providers and Microsoft accounts such as an Xbox LIVE account. Their source is Invited user. This type of account is useful when external vendors or contractors need access to your Azure resources. Once their help is no longer necessary, you can remove the account and all of their access.|





![tt](../../pictures/viewing_users0.png
![tt](../../pictures/viewing_users.png
![tt](../../pictures/viewing_my_users.png
![tt](../../pictures/view_peter_bosch.png

## Use roles to control resource access
10 minutes
Built-in Roles for Azure Resources (USES POWERSHELL)
Azure AD provides several built-in roles to cover the most common security scenarios. To understand how the roles work, let's examine three roles that apply to all resource types:

Owner, which has full access to all resources, including the right to delegate access to others.
Contributor, which can create and manage all types of Azure resources but can’t grant access to others.
Reader, which can view existing Azure resources.
Role definitions
Each role is a set of properties defined in a JavaScript Object Notation (JSON) file. This role definition includes a Name, Id, and Description. It also includes the allowable permissions (Actions), denied permissions (NotActions), and scope (for example, read access) for the role.
For the Owner role, that means all actions, indicated by an asterisk (*); no denied actions; and all scopes, indicated by a forward slash (/).
You can get this information using the Powershell Get-AzureRmRoleDefinition cmdlet. Try typing the following command into the Cloud Shell on the right.


![tt](../../pictures/Get-AzureRmRoleDefinition-Name_Owner.png)

Examine the built-in roles

|Next, let's explore some of the other built-in roles.|
|----------------------------------------------|
|Open the Azure portal |
|Select Resource groups from the left sidebar.|

![tt](../../pictures/Get-AzureRmRoleDefinition-Name_Owner.png
![tt](../../pictures/resource_group.png

|Next, let's explore some of the other built-in roles.|
|----------------------------------------------|
|Select the resource group.|


|Next, let's explore some of the other built-in roles.|
|----------------------------------------------|
|Select the Access control (IAM) item from the sidebar menu.|

|Next, let's explore some of the other built-in roles.|
|----------------------------------------------|
|Select the Roles tab as shown below to see the list of available roles.|


## Adding users
You can add cloud identities to Azure AD in multiple ways:

## Syncing an on-premises Windows Server Active Directory
Azure AD Connect is a separate service that allows you to synchronize a traditional Active Directory with your Azure AD instance. This is how most enterprise customers add users to the directory. The advantage to this approach is users can use single-sign-on (SSO) to access local and cloud-based resources.



## https://endpoint.microsoft.com


![tt](../../pictures/Get-AzureRmRoleDefinition-Name_Owner.png)
![tt](../../pictures/my_endpoint-microsoft-com.png)
![tt](../../pictures/resource_group.png)
![tt](../../pictures/use_portal_users.png)


In addition to Name and User name, you can add profile information, like Job Title and Department.

![tt](../../pictures/create_user.png)


The default behavior is to create a new user in the organization. The user will have a username with the default domain name assigned to the directory such as alice@staracoustics.onmicrosoft.com.

You can also invite a user into the directory. In this case, an email is sent to a known email address and an account is created and associated with that email address if they accept the invitation.

![tt](../../pictures/create_user_invite.png)


The invited user will need to create an associated Microsoft account (MSA) if that specific email address isn't associated with one and the account will be added to the Azure AD as a guest user.

## Use the command line
If you have a lot of users to add, a better option is to use a command-line tool. You can use the New-AzureADUser Azure PowerShell command to add cloud-based users.

````
# Create a password object
$PasswordProfile = New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile

# Assign the password
$PasswordProfile.Password = "<Password>"

# Create the new user
New-AzureADUser -AccountEnabled $True -DisplayName "Abby Brown" -PasswordProfile $PasswordProfile -MailNickName "AbbyB" -UserPrincipalName "AbbyB@contoso.com"
````

````
The command will return the new user object you created.
Output
Copy
ObjectId                             DisplayName UserPrincipalName UserType
--------                             ----------- ----------------- --------
f36634c8-8a93-4909-9248-0845548bc515 Abby Brown  AbbyB@contoso.com Member
````


If you prefer a more traditional command-line, you can use the Azure CLI:

````
az ad user create --display-name "Abby Brown" \
                  --password "<password>" \
                  --user-principal-name "AbbyB@contoso.com" \
                  --force-change-password-next-login true \
                  --mail-nickname "AbbyB"
````

![tt](../../pictures/az-cli_ad_user_create.png)

