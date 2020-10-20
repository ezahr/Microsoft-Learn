## 7 Manage device identity with Azure AD join and Enterprise State Roaming




[Manage identity and access in Azure Active Directory](https://docs.microsoft.com/en-us/learn/paths/manage-identity-and-access/)


1 hr 14 min remaining Learning Path 6 of 9 modules completed

Beginner
Intermediate
Solutions Architect
Administrator
Security Engineer
Azure
CLIs
Azure Portal
Azure Active Directory
Learn how to work with subscriptions, users, and groups by configuring Microsoft Azure Active Directory for workloads. This learning path can help you prepare for the Microsoft Certified: Azure Security Engineer Associate certification.

Prerequisites
None


Introduction
2 minutes
Suppose you work for a large book publisher that's deploying Windows 10 to employees' laptops. Your organization uses Azure Active Directory (Azure AD) and Azure Multi-Factor Authentication. With these services, you can manage user identities and help protect the organization's resources.

You want to add another layer of security for devices. Specifically, you need to restrict access to the organization's resources to only devices that your organization manages and that your mobile device management (MDM) system considers compliant. You also want to improve your organization's experience when switching between devices.

Learning objectives
In this module, you'll:

Describe options to manage device identities in Azure AD
Configure Azure AD join to manage device identities
Configure Enterprise State Roaming to reduce the time that users need to configure a new device
Prerequisites
Basic knowledge of Azure AD features such as Azure AD Connect, Azure AD Seamless Single Sign-On, and Multi-Factor Authentication
Basic understanding of MDM software like Microsoft Intune
Next unit: What is device identity in Azure

What is device identity in Azure?
7 minutes
In this unit, you'll learn about device identity and registration options, and how they apply to various devices. You'll see how you can apply conditional access to improve access control with your devices. Finally, you'll look at the benefits, and the considerations, of using device identity in Azure.

Basics of device identity
Device identity in Azure Active Directory (Azure AD) helps you control the devices that you add to your organization's Azure AD instance. It also helps you control the data, resources, and assets that those devices can access. It provides a framework to implement device-based conditional access. You can use a device-based conditional access policy to limit device access to your organization's assets.

Today's work environment extends beyond the controllable boundaries of your on-premises workspace. Your staff can now work in various locations, not only in their home country or region but also abroad. Users can access a broader range of technologies. Some of these technologies are owned by your organization, but others aren't.

The challenge faced by IT staff is how to give users flexibility while protecting the company's data. You want to support your users and enable them to be productive wherever they're working, on whatever device they're using. But you still need to keep your organization's resources and assets safe.

Finding a balance between protecting assets and allowing users greater flexibility in the devices they use is at the heart of device identity. Every device that you want to connect to your network must be known. Tools such as Microsoft Intune can enhance what's known about a device by ensuring compliance with organizational requirements.

Combining Azure AD with single sign-on means that users can access services and apps through any device. This outcome meets your organization's need to protect its resources and assets, and gives users the flexibility they want.

Device registration options
You have three device registration options to add a device to Azure AD:

Azure AD registered: These devices fall into the Bring Your Own Device (BYOD) category. They're typically privately owned, or they use a personal Microsoft account or another local account. This method of device registration is the least restrictive because it supports devices running Windows 10, iOS, iPadOS, Android, and macOS. Device security is typically provided from a password, a PIN, a pattern, or Windows Hello.

Azure AD joined: These devices are owned by your organization. Users access your cloud-based Azure AD instance through their work account. Device identities exist only in the cloud. This option is available only to Windows 10 or Windows Server 2019 devices. Windows Server 2019 Server Core installation isn't supported. Security for this option uses either a password or Windows Hello.

Hybrid Azure AD joined: This option is similar to Azure AD joined. The devices are owned by the organization, and they're signed in with an Azure AD account that belongs to that organization. Device identities exist in the cloud and on-premises. The hybrid option is better suited to organizations that need on-premises and cloud access. This option supports Windows 7, 8.1, and 10, and Windows Server 2008 or later.

## Conditional access
Conditional access in Azure AD uses data from sources known as signals, validates them against a user-definable rule base, and chooses the best outcome to enforce your organization's security policies. Conditional access enables device identity management, but conditional access policies can be complex.

![tt](./../pictures/Conditional-access.png)

At their simplest, these policies can be thought of as "if-then" statements. If a user wants access to a resource, then they must fulfill the condition to complete the request. Example: A payroll manager wants to access the payroll application. The conditional access policy requires them to use a compliant device and to complete multifactor authentication to access the application.

## Common signal types
Conditional access uses many common signal types to make a decision on which outcome to recommend.

![tt](./../pictures/Common-signal-types.png)


Common decisions
Conditional access evaluates the signals and provides a decision:

Block access, which is the most restrictive.
Grant access, which is the least restrictive but might require additional criteria before allowing access.

|Those criteria can be one or more of:|
|-------------------------------------------|
|Multifactor authentication|
|Device marked as compliant|
|Device that's hybrid Azure AD joined|
|Approved application|
|Need for an app protection policy|


If your organization uses Azure Multi-Factor Authentication, users don't have to do multifactor authentication when they're using a device that's mobile device management (MDM) compliant and Azure AD joined. You can select the option Require one of the selected controls with your grant controls selected. If you need extra security for something like a payroll app, select Require all the selected controls to require multifactor authentication and a compliant device.

![tt](./../pictures/grant.png)


Many organizations have common access concerns that conditional access policies can help with, such as:

|Commonly applied policies|
|--------------------------------------------|
|Requiring multifactor authentication for users who have administrative roles.|
|Requiring multifactor authentication for Azure management tasks.|
|Blocking sign-ins for users who are trying to use older authentication protocols.|
|Requiring trusted locations for Azure Multi-Factor Authentication registration.|
|Blocking or granting access from specific locations.|
|Blocking risky sign-in behaviors.|
|Requiring organization-managed devices for specific applications.|


Conditional access policies are applied after a user has successfully completed first-factor authentication, typically with a username and password. These policies aren't a substitute for first-factor authentication. They're used to assess factors like device, location, and application, and to assess the risk in real time.


## To make your policy work, you must configure:

SELECTIONS TO CREATE A CONDITIONAL ACCESS POLICY
What	How	Why
Cloud apps	Select one or more apps.	The goal of a conditional access policy is to enable you to control how authorized users can access cloud apps.
Users and groups	Select at least one user or group that is authorized to access your selected cloud apps.	A conditional access policy that has no users and groups assigned is never triggered.
Access controls	Select at least one access control.	If your conditions are satisfied, your policy processor needs to know what to do.

## Benefits of device identity management
Some of the benefits of using device identity, combined with conditional access in Azure AD, are:

The combination simplifies the procedure for adding and managing devices in Azure AD.
The combination reduces the friction for users when they're switching between devices.
Azure AD supports MDM tools such as Microsoft Intune.
You can use single sign-on (SSO) with any registered or joined device.
Considerations for using device identity management
When you're evaluating device identity, consider the following factors:

Using the Azure AD joined or hybrid option limits you to using a Windows-based or Windows Server-based operating system on the device. Conditional access requires an Azure AD Premium P1 license or a Microsoft 365 Business license.


![tt](./../pictures/check-your_knowledge.png)

![tt](./../pictures/check-your_knowledge2.png)


What is Azure AD join?
7 minutes
You now have a better understanding of device identity and conditional access. You want to investigate Azure Active Directory (Azure AD) join and how it might be used to improve device management for both Azure and on-premises Active Directory Domain Services.

In this unit, you'll learn about Azure AD join, and how to use it for infrastructure and device management.

Basics of Azure AD join
With Azure AD join, you can join devices to your Azure Active Directory organization without needing to sync with an on-premises Active Directory instance. Azure AD join is best suited to organizations that are principally cloud based, although it can operate in a hybrid cloud and on-premises environment.

Supported devices
Azure AD join works with Windows 10 or Windows Server 2019 devices. Windows Server 2019 Server Core installation isn't supported. If you're using an earlier Windows operating system, you'll need to upgrade to Windows 10 or Windows Server 2019.

Identity infrastructure
Decide what identity infrastructure model best supports your organization's needs:

Managed environment: This environment uses pass-through authentication or password hash sync to provide single sign-on (SSO) to your devices.
Federated environments: These environments require the use of an identity provider. That provider must support the WS-Trust and WS-Fed protocols for Azure AD join to work natively with Windows devices. WS-Fed is required to join a device to Azure AD. WS-Trust is needed to sign in to an Azure AD joined device.
Smart cards and certificate-based authentication: These methods aren't valid ways to join devices to Azure AD. But, if you have Active Directory Federation Services configured, you can use smart cards to sign in to Azure AD joined devices. We recommend that you use a service like Windows Hello for Business, which supports passwordless authentication to Windows 10 devices.
Manual user configuration: If you create users in your on-premises Active Directory instance, you need to synchronize the accounts to Azure AD by using Azure AD Connect. If you create users in Azure AD, no additional setup is needed.
Device management
Azure AD join uses the mobile device management (MDM) platform to manage devices attached to Azure AD. MDM provides a means to enforce organization-required configurations like requiring storage to be encrypted, password complexity, software installations, and software updates.

The latest versions of Windows 10 have a built-in MDM client that works with all compatible MDM systems.

To manage your Azure AD joined devices, there are two approaches:

MDM only: All joined devices are managed exclusively through an MDM provider, like Intune. If your organization uses group policies, you'll need to review your MDM policy for support.

Co-management: All joined devices use a combination of a locally installed System Center Configuration Manager agent and your MDM provider. Microsoft Intune provides co-management capabilities through Configuration Manager. You use Configuration Manager to manage the device while MDM delivers user-management policies.

We recommend that you use the MDM-only approach to manage all Azure AD joined devices.

Considerations for resources and application access
For the best user experience and to improve access to your application, consider moving all applications and resources to Azure. Although that might be possible in some cases, it isn't always practical. In this section, we'll explore access options for your applications and resources:

Cloud-based applications: Any migrated apps and all new applications will be added to the Azure AD app gallery. Users of Azure AD join can use SSO to access those applications. The majority of browsers support SSO. Azure AD join provides SSO support for device access to applications that are still using Win32.

On-premises web applications: Any bespoke or custom-made software that's hosted on-premises can still be accessed through Azure AD join. Access to those applications needs each user to add the app to their trusted sites or intranet zone, depending on where the app exists. This action allows the application to use Windows-integrated authentication without prompting the user to authenticate.

Other devices: This option includes existing applications through earlier protocols, and on-premises network shares. Both are available to Azure AD joined devices through SSO, if the device is connected to your domain controller.

Printer resources: These resources won't automatically be available through Azure AD join. Users can still connect to a printer directly, by using its UNC path.

Provisioning options
When you're deploying Azure AD join, you have three choices for how devices are provisioned and joined to Azure AD:

Self-service: Requires users to manually configure the device during the Windows out-of-box experience (OOBE) for new devices, or by using the Windows settings for older devices. Self-service is better suited to users who have a strong technical background.

Windows Autopilot: Allows you to preconfigure Windows devices, including automatically joining the device to your Active Directory organization, automatic MDM enrollment, and creating customer OOBE content. This approach simplifies the management and deployment of devices across your organization. The Windows device can be provisioned and deployed. The user completes the OOBE as if they're a new user.

Bulk enrollment: Lets you set up a provisioning package that applies to a large number of new Windows devices at the same time.


![tt](./../pictures/Provisioning-options.png)


![tt](./../pictures/device_settings.png)


|Field|	Description|
|----------------------------|----------------------------------------|
Users may join devices to Azure AD	|All allows for any user to join their device. Selected allows you to add specific users that can join devices. None prevents all users from joining their devices.|
|Additional local administrators on Azure AD |joined devices	Lets you specify other users to be included as local administrators on all joined devices. By default, this option is enabled. Azure AD adds the global administrator and device administrator roles as local administrators on devices.|
|Users may register their devices with Azure AD|	Allows users to register their devices with Azure AD join. If you're using Microsoft Intune or mobile device management for Microsoft 365, device registration is required. If either of these services is configured in your Azure AD organization, All is selected and this option is disabled.|
|Require Multi-Factor Authentication to join devices	|Lets you enforce Azure Multi-Factor Authentication when the device joins Azure AD. For users who join devices to Azure AD by using Multi-Factor Authentication, the device itself becomes a second factor.|
|Maximum number of devices per user|	Lets yo1u specify the maximum number of devices a user can have in Azure AD. If a user reaches this maximum, they need to remove a device to add a new one.|


For our scenario, we can add a pilot group of users to try AD join. In that case, choose Users may join devices to Azure AD > Selected, and then add members of your pilot group. When you're ready to deploy Azure AD join to your entire Azure AD organization, select All.


## Mobility settings
You might need to add an MDM provider before you can configure mobility settings. To add your MDM provider, go to Azure Active Directory > Mobility (MDM and MAM) > Add application.


![tt](./../pictures/add_an_application.png)

When you have your MDM provider added, you can configure the following mobility settings:

## MOBILITY SETTINGS

|Mobility setting	|description|
|-------------------------|----------------------------------------------|
|MDM user scope|	Select None, Some, or All. If the user is in the MDM scope and you have an Azure AD Premium subscription, MDM enrollment is automated along with Azure AD join. All users within the scope must have an appropriate license for your MDM. If not, the MDM enrollment fails and Azure AD join is rolled back. If the user isn't in the MDM scope, Azure AD join finishes without any MDM enrollment. The device is an unmanaged device.|
|MDM URLs|	The three URLs related to your MDM configuration are MDM terms of use URL, MDM discovery URL, and MDM compliance URL. Each URL has a predefined default value. If these fields are empty, contact your MDM provider for more information.|
|MAM settings	|Mobile application management (MAM) does not apply to Azure AD join.|

Recall that you need to restrict access to the organization's resources to only devices that your organization manages and that your MDM system considers compliant. For our scenario, we'd want to add our organization's MDM provider and select MDM user scope > All.



## User experience when joining a Windows 10 device
You've given a new device to a tech-savvy employee. They'll use the self-service approach to join the device to your Active Directory organization, which is using Multi-Factor Authentication. The following steps show you what that workflow looks like:

After starting the device, the employee follows the prompts to set it up, including customizing their region and selecting a language.

![tt](./../pictures/User-experience-when-joining-a-Windows10-device.png)

The employee signs in with the credentials that your organization has supplied.

The employee is prompted with a multifactor authentication challenge.

Azure AD checks the configuration settings to see if the device should be enrolled in MDM.

When the configuration check is successful, the device is registered with the organization's Azure AD instance. If MDM is being used, the device is enrolled and managed.

Check your knowledge
1. What provisioning options are available through Azure AD join?

Self-service by using the Windows out-of-box experience (OOBE), Windows Autopilot, or bulk enrollment
Self-service by using MDM, Windows Autopilot, or bulk enrollment

Windows Autopilot or bulk enrollment
2. What happens when a device isn't in the MDM scope?

The user is asked to add the device to MDM before the device can join Azure AD.
The device can't join Azure AD until the device has been registered with MDM.

The Azure AD join finishes without the enrollment to MDM.

![tt](./../pictures/provisioning-options-are-available-through-Azure-AD-join.png)


## What is Enterprise State Roaming?
7 minutes
Your organization wants to improve the security of its devices. So far, you've seen how security is enhanced by using device identity and Azure Active Directory (Azure AD) join. But you need to maintain the security seamlessly when a user switches between devices. You want to see the options that Azure offers to allow users to transition their accounts between devices. Users need to maintain data and settings without increasing technical overhead or maintenance.

In this unit, you'll learn about Enterprise State Roaming. You'll learn how to enable it, where the user's application and settings data is stored, and how long the data is stored.

Basics of Enterprise State Roaming
Enterprise State Roaming enables users of Windows 10 devices to sync settings and application data with their organization's cloud service. When synchronization is enabled, it takes place automatically. You can enable all applicable device users, or select specific users or groups based on your organization's needs. With Enterprise State Roaming, users' settings and application data follow them when they switch devices.

Key benefits of using Enterprise State Roaming are:

Separation of corporate and consumer data.
Enhanced security, because all applicable device data is encrypted through Azure Rights Management before synchronizing with the cloud. All stored data remains encrypted.
Better management and monitoring, so you decide who can sync their data and from which devices.
Enterprise State Roaming requires a Premium Azure Active Directory subscription.

Data that syncs and roams
Windows settings: The PC settings that are built into the Windows operating system. Generally, these settings personalize your PC. They include the following categories:

Theme, which includes features such as desktop theme and taskbar settings.
Internet Explorer settings, including recently opened tabs and favorites.
Microsoft Edge browser settings, such as favorites.
Passwords, including internet passwords, Wi-Fi profiles, and others.
Language preferences, which include settings for keyboard layouts, system language, date and time, and more.
Ease of access features, such as high-contrast theme, Narrator, and Magnifier.
Other Windows settings, such as mouse settings.
Application data: Universal Windows apps can write settings data to a roaming folder. Any data written to this folder will automatically be synced. It's up to the individual app developer to design an app to take advantage of this capability.

Enabling Enterprise State Roaming
Enterprise State Roaming requires a device to authenticate with a known Azure AD identity. For Azure AD joined devices, this identity is the account that the user first signed in with.

To enable Enterprise State Roaming, go to Azure Active Directory > Devices > Enterprise State Roaming.

 ![tt](./../pictures/AzureActiveDirectory-Devices-Enterprise-State Roaming.png)

##  Data storage
Enterprise State Roaming stores the user data in a geographical region that's nearest to your Azure AD instance. There are three geographic regions: North America (USA); Europe, the Middle East, and Africa (EMEA); and Asia-Pacific (APAC). Although tenant data will be hosted in the nearest region, user data can be hosted in one or more of these regions.

The country or region for your tenant is defined when Azure AD is set up. It can't be changed.

## Data retention
All Enterprise State Roaming data persists in the cloud until it's explicitly deleted or becomes stale. Any deleted data is automatically kept for a minimum of 90 days. After 90 days, you can't restore the deleted data from the cloud.

## Explicit data deletion
Explicit data deletion occurs when an Azure administrator acts on a user or an organization within Azure AD, or needs to request that specific roaming data is removed for a user.

User deletion: When the administrator removes a user from Azure AD, any associated enterprise roaming data is automatically deleted.

Azure AD organization deletion: When the administrator removes a directory, all user settings or data stored in that directory is automatically discarded.

On Request deletion: Use this option to remove a specific user's roaming data. The administrator needs to raise an Azure support ticket for this option.

## Stale data deletion

Any Enterprise State Roaming data that hasn't been accessed during the past year is automatically treated as stale data. Stale data is deleted from the host cloud storage. The retention period of deleted data is 90 days.

## Deleted data recovery
After the retention period elapses, data is permanently deleted from the cloud and can't be recovered. But you can restore the data from the device when it next connects to the cloud.The data retention periods can't be changed.

Check your knowledge
1. What is classified as stale data?

Any data that hasn't been accessed for more than 90 days
Any data that hasn't been accessed for more than 180 days

Any data that hasn't been accessed for one year or more
2. Can you name one of the benefits of using Enterprise State Roaming?

Enhanced security
Separation of cloud and device data
Improved consumer data management


Summary
2 minutes
In this module, you've been introduced to device identities and how they bring better access control to an organization's resources. You've explored how Azure Active Directory (Azure AD) join works, and how it supports self-service and Bring Your Own Device (BYOD).

You've learned how, with conditional access, you can control when and how a user will access your corporate resources. You've also seen how to use Enterprise State Roaming to separate corporate data from consumer data. Enterprise State Roaming allows for settings to move with the user when they switch devices, without a lengthy setup process.

Learn more

[Plan your conditional access deployment in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/plan-conditional-access)
[Enroll Windows devices in Intune by using the Windows Autopilot](https://docs.microsoft.com/en-us/mem/intune/enrollment/enrollment-autopilot)
[How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/en-us/azure/active-directory/devices/azuread-join-sso)
[Manage device identities using the Azure portal](https://docs.microsoft.com/en-us/azure/active-directory/devices/device-management-azure-portal)
[Manage stale devices in Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/devices/manage-stale-devices)
[Manage the local administrators group on Azure AD joined devices](https://docs.microsoft.com/en-us/azure/active-directory/devices/assign-local-admin)


## Allow users to reset their password with Azure Active Directory self-service password reset
31 min
Module
6 Units
Beginner
Administrator
Solutions Architect
Azure
Azure Active Directory
Evaluate self-service password reset to allow users in your organization to reset their passwords or unlock their accounts. Set up, configure, and test self-service password reset.

Learning objectives
In this module, you will:

Decide whether to implement self-service password reset.
Implement self-service password reset to meet your requirements.
Configure self-service password reset to customize the experience.

## Introduction
2 minutes
Suppose you're an IT administrator for a large retail organization. Your organization has started using Azure Active Directory (Azure AD) to allow employees to securely sign in and use software as a service (SaaS) apps, and access the organization's resources in Microsoft 365. You're overwhelmed with password reset requests because you currently reset employees' passwords manually. To get these employees back to being productive quickly and reduce your workload, you decide to evaluate and set up self-service password reset in Azure AD.

In this module, you'll learn how Azure supports this feature and how to set it up.

By the end of this module, you'll be able to configure self-service password reset in Azure AD.

Learning objectives

|In this module, you will:|
|-----------------------------------------------------|
|Decide whether to implement self-service password reset.|
|Implement self-service password reset to meet your requirements.|
|Configure self-service password reset to customize the experience.|
|Prerequisites|
|Basic understanding of Azure Active Directory|


Next unit: What is self-service password reset in Azure Active Directory?


## What is self-service password reset in Azure Active Directory?
7 minutes
You've been asked to assess ways to reduce help-desk costs in your retail organization. You've noticed that support staff spend much of their time resetting passwords for users. Users often complain about delays with this process. The delay impacts their productivity. You want to understand how you can configure Azure to enable users to manage their own passwords.


In this unit, you'll learn how self-service password reset (SSPR) works in Azure Active Directory (Azure AD).

## Why use SSPR?
In Azure AD, any user can change their password if they're already signed in. But if they're not signed in and forgot their password or it's expired, they'll need to reset their password. With SSPR, users can reset their passwords in a web browser or from a Windows sign-in screen to regain access to Azure, Microsoft 365, and any other application that uses Azure AD for authentication.

SSPR reduces the load on administrators, because users can fix password problems themselves, without having to call the help desk. Also, it minimizes the productivity impact of a forgotten or expired password. Users don't have to wait until an administrator is available to reset their password.

## How SSPR works
The user initiates a password reset either by going directly to the password reset portal or by selecting the Can't access your account link on a sign-in page. The reset portal takes these steps:

Localization: The portal checks the browser's locale setting and renders the SSPR page in the appropriate language.
Verification: The user enters their username and passes a captcha to ensure that it's a user and not a bot.
Authentication: The user enters the required data to authenticate their identity. They might, for example, enter a code or answer security questions.

Password reset: If the user passes the authentication tests, they can enter a new password and confirm it.
Notification: A message is usually sent to the user to confirm the reset.
There are several ways you can customize the SSPR user experience. For example, you can add your company logo to the sign-in page so users know that they're in the right place to reset their password.

## Authenticate a password reset
It's critical to verify the identity of a user before you allow a password reset. Malicious users might exploit any weakness in the system to impersonate that user. Azure supports six different ways to authenticate reset requests.

As an administrator, you choose the methods to use when you configure SSPR. Enable two or more of these methods so that users can choose the ones that they can use easily. The methods are:

## AUTHENTICATE A PASSWORD RESET
|Authentication method	|How to register	|How to authenticate for a password reset|
|Mobile app notificatio|n	Install the Microsoft Authenticator app on your mobile device, and then register it on the multifactor authentication setup page.|	Azure sends a notification to the app, which you can either verify or deny.|
|Mobile app code|	This method also uses the Authenticator app, and you install and register it in the same way.|	Enter the code from the app.|
|Email	|Provide an email address that's external to Azure and Microsoft 365.|	Azure sends a code to the address, which you enter in the reset wizard.|
|Mobile phone	|Provide a mobile phone number.|	Azure sends a code to the phone in an SMS message, which you enter in the reset wizard. Or, you can choose to get an automated call.|
|Office phone |	Provide a nonmobile phone number.	|You receive an automated call to this number and press #.
|Security questions	Select questions such as "In what city was your mother born?" and save responses to them.	Answer the questions.|

In free and trial Azure AD organizations, phone call options aren't supported.

## Require the minimum number of authentication methods

You can specify the minimum number of methods that the user must set up: one or two. For example, you might enable the mobile app code, email, office phone, and security questions methods and specify a minimum of two methods. Then users can choose the two methods they prefer, like mobile app code and email.

For the security question method, you can specify a minimum number of questions that the user must set up to register for this method. You also can specify a minimum number of questions that they must answer correctly to reset their password.

After your users register the required information for the minimum number of methods you've specified, they're considered registered for SSPR.

## Recommendations
Enable two or more of the authentication reset request methods.
Use the mobile app notification or code as the primary method, but also enable the email or office phone methods to support users without mobile devices.
The mobile phone method isn't a recommended method because it's possible to send fraudulent SMS messages.
The security question option is the least recommended method because the answers to the security questions might be known to other people. Only use the security question method in combination with at least one other method.
Accounts associated with administrator roles
A strong, two-method authentication policy is always applied to accounts with an administrator role, regardless of your configuration for other users.
The security questions method isn't available to accounts that are associated with an administrator role.
Configure notifications
Administrators can choose how users are notified of password changes. There are two options that you can enable:

Notify users on password resets: The user who resets their own password is notified to their primary and secondary email addresses. If the reset was done by a malicious user, this notification alerts the user, who can take mitigation steps.
Notify all admins when other admins reset their password: All administrators are notified when another administrator resets their password.
License requirements
The editions of Azure AD are free, Premium P1, and Premium P2. The password reset functionality you can use depends on your edition.

Any user who is signed in can change their password, regardless of the edition of Azure AD.

If you're not signed in and you've forgotten your password or your password has expired, you can use SSPR in Azure AD Premium P1 or P2. It's also available with Microsoft 365 Apps for business or Microsoft 365. SSPR isn't available in the free edition of Azure AD.

In a hybrid situation, where you have Active Directory on-premises and Azure AD in the cloud, any password change in the cloud must be written back to the on-premises directory. This writeback support is available in Azure AD Premium P1 or P2. It's also available with Microsoft 365 Apps for business.

Check your knowledge
1. When is a user considered registered for SSPR?

When they've registered at least one of the permitted authentication methods.
x When they've registered at least the number of methods that you've required to reset a password.
When they've set up the minimum number of security questions.

2. When you enable SSPR for your Azure AD organization...

Users can change their password when they're signed in.
Admins can reset their password by using one authentication method.
x Users can reset their passwords when they can't sign in.


Next unit: Implement Azure AD self-service password reset

mplement Azure AD self-service password reset
5 minutes
You've decided to implement self-service password reset (SSPR) in Azure Active Directory (Azure AD) for your organization. You want to start using SSPR for a group of 20 users in the marketing department as a trial deployment. If everything works well, you'll enable SSPR for your whole organization.

In this unit, you'll learn how to enable SSPR in Azure AD.

Prerequisites
Before you start to configure SSPR, you need these things in place:

An Azure AD organization. This organization must have at least a trial license enabled.
An Azure AD account with Global Administrator privileges. You'll use this account to set up SSPR.
A non-administrative user account. You'll use this account to test SSPR. It's important that this account isn't an administrator, because Azure AD imposes extra requirements on administrative accounts for SSPR. This user, and all user accounts, must have a valid license to use SSPR.
A security group to test the configuration with. The non-administrative user account must be a member of this group. You'll use this security group to limit who you roll SSPR out to.
If you don't already have an Azure AD organization that you can use for this module, we'll set one up in the next unit.

## Scope of SSPR rollout
There are three settings for the Self-service password reset enabled property:

Disabled: No users in the Azure AD organization can use SSPR. This value is the default.
Enabled: All users in the Azure AD organization can use SSPR.
Selected: Only the members of the specified security group can use SSPR. You can use this option to enable SSPR for a targeted group of users, who can test it and verify that it works as expected. When you're ready to roll it out broadly, set the property to Enabled so that all users have access to SSPR.
Configure SSPR
Here are the high-level steps to configure SSPR.

In the Azure portal, go to Active Directory > Password reset.

Properties:

## Enable SSPR.
You can enable it for all users in the Azure AD organization or for selected users.
To enable for selected users, you must specify the security group. Members of this group can use SSPR.


![tt](./../pictures/configure-SSPR.png)



## Exercise - Set up self-service password reset
10 minutes
This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox.
Due to the impact of the global health pandemic, Azure resources are being prioritized towards health and safety organizations. You may experience some issues when you deploy resources used in the exercises. Please try again or choose a different region. For more information, see Azure blog post - Update #3: Business continuity with Azure.


## Create an Azure AD organization
The default Azure Active Directory (Azure AD) organization in the Azure sandbox doesn't support SSPR. So in this exercise, let's create a second organization and switch to it.

Sign in to the Azure portal  with the same account you used to activate the sandbox.
Select Create a resource > Identity > Azure Active Directory.

![tt](./../pictures/Set-up-self-service-password-reset1.png)


On the Create tenant page, use these values, and then select Create.


|Property|	Value|
|-------------------|----------------------------------|
|Organization name|	Choose any organization name.|
|Initial domain name|	Choose a domain name that's unique within .onmicrosoft.com. Make a note of the domain you choose.|
|Country or region|	United States.|


## Create an Azure AD Premium P2 trial subscription

|Now activate a trial Premium subscription for the organization so that you can test SSPR.|
|-------------------------------------------------------------|
|Go to Azure Active Directory > Password reset.|
|Select Get a free Premium trial to use this feature.|
|Under AZURE AD PREMIUM P2, expand Free trial and then select Activate.|
|Refresh the browser to see the Password reset - Properties page.|

## Create a group
You want to roll out SSPR to a limited set of users first to make sure your SSPR configuration works as expected. Let's begin by creating a security group for the limited rollout. 
In the Azure AD organization you created, under Manage, select Groups.

|Select + New Group.|Enter the following values:|
|-------------------------|-----------------------------------|
|Setting	|Value|
|Group type	|Security|
|Group name	|SSPRTesters|
|Group description	|Testers of SSPR rollout|
|Membership type	|Assigned|

![tt](./../pictures/Set-up-self-service-password-reset2.png)

## Register for SSPR
Now that the SSPR configuration is complete, register a mobile phone number for the user you created.

In a new browser window, go to https://aka.ms/ssprsetup.

Sign in with the user name balas@organization-domain-name.onmicrosoft.com and the password that you noted earlier.

If you're asked to update your password, enter a new password of your choice. Make sure you note the new password.

Next to Authentication phone is not configured, select Set it up now.

Enter your mobile phone details.

![tt](./../pictures/Set-up-self-service-password-reset3.png)

## Test SSPR
Now let's test whether the user can reset their password.
In a new browser window, go to https://aka.ms/sspr.

For User ID, type balas@organization-domain-name.onmicrosoft.com. Replace "organization-domain-name" with the domain you used for your Azure AD organization.

![tt](./../pictures/Set-up-self-service-password-reset4.png)

## Exercise - Customize directory branding
5 minutes
This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox.
Due to the impact of the global health pandemic, Azure resources are being prioritized towards health and safety organizations. You may experience some issues when you deploy resources used in the exercises. Please try again or choose a different region. For more information, see Azure blog post - Update #3: Business continuity with Azure.

Suppose you've been asked to display your retail organization's branding on the Azure sign-in page to reassure users that they're passing credentials to a legitimate system.

Here, you'll learn how to configure this custom branding.

To complete this exercise, you must have two image files:

A page background image. This must be a PNG or JPG file, 1920 x 1080 pixels, and smaller than 300 KB.
A company logo image. This must be a PNG or JPG file, 280 x 60 pixels, and smaller than 10 KB.

## Customize Azure AD organization branding
Let's use Azure Active Directory (Azure AD) to set up the custom branding.

Sign in to the Azure portal  with the same account you used to activate the sandbox.

Go to your Azure AD organization by selecting Azure Active Directory. If you're not in the right Azure AD organization, go to your Azure profile in the upper-right corner and select Switch directory to find your organization.

Under Manage, select Company branding > Configure.

Next to Sign-in page background image, select Browse. Select your page background image.

Next to Banner logo, select Browse. Select your logo image.

## Test the organization's branding

Now, let's use the account that we created in the last exercise to test the branding.
In a new browser window, go to https://login.microsoft.com.
Select the account for Bala Sandhu. Your custom branding is displayed.


![tt](./../pictures/SCustomize-Azure-AD-organization-branding1.png)

![tt](./../pictures/SCustomize-Azure-AD-organization-branding2.png)


Next unit: Summary


Summary
2 minutes
In this module, you've learned how you can use self-service password reset (SSPR) in Azure Active Directory (Azure AD) to allow users to reset their forgotten or expired passwords. An administrator doesn't have to do the password reset. SSPR is secured by authentication methods of your choice. These methods can include a mobile authentication app, a code sent to you by an SMS text message, or security questions.

SSPR helps reduce the amount of work required from administrators. It also minimizes the productivity impact for users when they forget their password.

Clean up
Remember to clean up after you've finished.

Delete the user you created in Azure AD. Go to Azure Active Directory > Manage > Users. Select the user, and select Delete user.
Turn off self-service password reset. Go to Azure Active Directory > Manage > Password reset. Under Self service password reset enabled, select None.
If you created a Premium trial Azure AD tenant for this module, you can delete the tenant 30 days after the trial has expired.

[Quickstart: Self-service password reset](https://docs.microsoft.com/en-us/azure/active-directory/authentication/quickstart-sspr)
[How it works: Azure AD self-service password reset](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-sspr-howitworks)
[Deploy Azure AD self-service password reset](https://docs.microsoft.com/en-us/azure/active-directory/authentication/howto-sspr-deployment)


Add custom domain name to Azure Active Directory
18 min
Module
5 Units
Beginner
Administrator
Azure
Azure Active Directory
Add your custom domain to Azure Active Directory. Add DNS information to the domain registrar. Verify your custom domain name in the Azure portal and set it as the primary.

Learning objectives
In this module, you will:

Add a custom domain name in Azure Active Directory
Identify the common issues when verifying the custom domain name


ntroduction
2 minutes
You can add custom domain names to Azure Active Directory (Azure AD). After you add the domain names, your employees can use memorable and branded usernames to access your company's resources.

Your organization used Azure to develop and test a pilot project. It has now decided to make Azure available to the entire company. You're the organization's Global Administrator in Azure AD. You're going to set up accounts for all your employees.

You want to create usernames that are familiar to your users. Their Azure sign-in names need to be memorable. Also, their Azure AD accounts should clearly be associated with your organization. You have a new custom domain name that your organization bought from a domain name registrar. Before you create the user accounts, you want to add your organization's custom domain name to Azure AD.

This module explains how Azure AD supports custom domain names and shows how to add them. The final unit discusses some common problems you might see and how to solve them.

Learning objectives
In this module, you'll:

## Add a custom domain name in Azure Active Directory.
Identify common problems when you verify the custom domain name.
Prerequisites
Familiarity with identity and access-management concepts in Azure Active Directory
Basic knowledge of networking concepts like Domain Name System (DNS)
Next unit: What are domain names in Azure Active Directory?

## What are domain names in Azure Active Directory?
5 minutes
Domain names give you access to networked resources. The most obvious resources are websites on the internet. You can also associate services like Exchange Server, Microsoft 365, and Azure Active Directory (Azure AD) with a domain name.

Before you start to create company Azure apps and teach employees to use them, you want to see how Azure AD supports custom names.

In this unit, you'll explore how to use domain names in Azure AD and how subdomains are supported.

## What are custom domain names in Azure?  ontoso.onmicrosoft.com.
When you create an Azure subscription, you specify a default domain for your organization. The domain is in the format something.onmicrosoft.com. An example is contoso.onmicrosoft.com.


![tt](./../pictures/contoso-onmicrosoft-com.png)

Azure provides the default domain name onmicrosoft.com to all Azure AD organizations. You're free to use it in your organization to create users and grant them access to resources. If your company chooses this approach, your users sign in with username@something.onmicrosoft.com.

You can associate a domain name that your company owns with Azure AD to make the sign-in names more memorable and identifiable for your organization. In Azure AD, you add your domain name as a custom domain name. For our scenario, let's say your company owns proseware.com. If you add that domain name as a custom domain in Azure AD, your users sign in with names in the format username@proseware.com.

After users sign in, Azure AD's access management features control their access to external Microsoft services. Such services include Microsoft 365 and the Azure portal. With Azure AD, users can also access your company's internal resources like intranets and cloud apps developed in-house.

## Buy a domain name
You can buy a domain name by using Azure App Service domains or another domain name registrar. App Service domains are top-level domains that Azure directly manages. They make it easy to manage custom domains for App Service.

## Add a domain name to Azure
If your organization already added a custom domain for a Microsoft 365 subscription, you likely don't need to add it to Azure AD. The domain is listed and available to use as the primary domain.

If you set up Microsoft 365 in an organization different than your Azure subscription, or if you want to use a different domain, you might need to add a custom domain to Azure AD.

You can add up to 900 managed domain names to your Azure AD organization.


## Add a subdomain
After you add the custom domain and it's verified, Azure AD automatically verifies any subdomains you add. The subdomains www.proseware.com and sandbox.proseware.com are examples.

## Manage DNS records
Your domain name would be useless without the Domain Name System (DNS). This distributed system of computers provides a lookup database that associates a domain name with DNS records. One domain name can have alias records that point to:

Web servers by using A, AAAA, and CNAME records.
Email services by using MX records.
Name servers by using NS records.
Proof of ownership by using TXT records.
You can manage DNS records with the company that sold you the domain name. Or you can switch the DNS provider by changing the name server associated with your domain. If you'd like to centralize DNS management with your other infrastructure, take a look at Azure DNS.

Check your knowledge
1. What types of custom domain names are supported?

Only registered generic top-level domains.
Only registered country code top-level domains.
x Any registered domains that aren't already being used.

You can use any registered domain as long as an Azure AD organization isn't already using it.
2. Which resources can a custom-domain Azure AD account access?

Only internal resources.

x Both internal and external resources.
Azure AD accounts can access both internal and external resources.
Only external resources.



## Next unit: Add a custom domain name in Azure Active Directory

Add a custom domain name in Azure Active Directory
5 minutes
You use Azure to add your organization's custom domain name and allow employees to create memorable usernames.

In this unit, you'll see how to:

Associate your custom domain with an existing Azure Active Directory (Azure AD) organization.
Set the custom domain to be the primary domain.
Add users.
You can't complete this unit unless you've purchased a domain name and registered it with a Domain Name System (DNS) provider.

The following steps walk through the process to add a custom domain name to Azure. If you own an unused domain name, you can follow along in your own Azure AD organization.



## Add a custom domain name to Azure AD
In our scenario, your company has an Azure AD organization where you can add the domain name.

In Azure AD, under Manage select Custom domain name.

![tt](./../pictures/Azure_AD_under_Manage_select_Custom_domainname.png)


![tt](./../pictures/Azure_AD_under_Manage_select_Custom_domainname2.png)


## Add your DNS information to the domain registrar
Go to your domain registrar.

Create records for your domain based on the DNS information you copied from Azure. The following screenshot shows a text record added to Azure DNS. Azure DNS is acting as the domain registrar.

  
![tt](./../pictures/Add-your-DNS-information-to-the-domain-registrar.png)


## Verify your custom domain in Azure

In Azure AD, under Manage select Custom domain name.
Select your custom domain name.
Select Verify.

![tt](./../pictures/Verify-your-custom-domain-in-Azure.png)

If Azure verifies that the correct record exists, the domain name status changes to "Verified."


![tt](./../pictures/To-add-a-subdomain.png)


![tt](./../pictures/Verify-your-custom-domain-in-Azure2.png)


## Manage custom domain names by using Azure PowerShell
You might prefer to manage your domain names by using Azure PowerShell.

|New-AzureADDomain:| Creates a new domain. Use the parameter -IsDefault to set the domain name as the primary domain name.|
|Confirm-AzureADDomain:| Lets you try to validate the ownership of a domain.|
|Set-AzureADDomain:| Updates a domain name and can set the domain to the primary domain name.|
|Remove-AzureADDomain:| Deletes a domain from Azure AD.|

## Add a user
After you add a custom domain name and set it to be the primary domain, add users.

|In the Azure portal, go to Azure Active Directory.|
|On the left side of the pane, under Manage select Users.|
|Select + New user.|


![tt](./../pictures/Manage-custom-domain-names-by-using-Azure-PowerShell)


heck your knowledge
1. How do you verify domain ownership?

x The Azure portal provides a TXT or MX record you add through your DNS provider.
You can choose to add either TXT or MX records for your domain.
In the Azure portal, add the domain name to a DNS zone associated with your subscription.
The Azure portal prompts you to set up single sign-on for your domain.

2. What is the default domain name before a custom domain is created?

companyname.onazure.com
# companyname.onmicrosoft.com
The URL is defined when you create an Azure AD organization and is in the form of something.onmicrosoft.com.
onmicrosoft.companyname.com



## Solve common problems when adding a custom domain name
5 minutes
Although the process of adding a custom domain name is simple, you might face a few problems.

Unknown to you, some members of your sales department have started using Power BI. They signed up with their @proseware.com work email addresses. This action created an unmanaged Azure Active Directory (Azure AD) organization with users in that team.

In this unit, you'll resolve the unmanaged Azure AD organization problem, explore other problems, and see how to resolve them.

A custom domain name is under an unmanaged organization
If members of your organization sign up for another Microsoft service like OneDrive or Power BI, their email domain is used to create an unmanaged Azure AD organization. This organization or directory is useable for only that service. You can't add it as a custom domain in Azure AD.

You have two options to resolve this problem. Which you use depends on the service they signed up for.

Internal admin takeover: Add yourself as the global administrator for the unmanaged organization.
External admin takeover: Add the Domain Name System (DNS) domain name to your managed Azure AD organization.
The best solution is external admin takeover. Unfortunately, that's not an option for some services. The following table lists your option for each service.

A CUSTOM DOMAIN NAME IS UNDER AN UNMANAGED ORGANIZATION
Service	Solution
SharePoint	Internal admin takeover
OneDrive	Internal admin takeover
Microsoft 365	Internal admin takeover
Power BI	External admin takeover
Azure Rights Management	External admin takeover
Exchange Online	External admin takeover
Dynamics 365	External admin takeover
Because the sales team signed up for Power BI in this scenario, you can do an external admin takeover. The steps are the same as for adding a custom domain. The unmanaged organization won't stop you from completing those steps.

After you add your custom domain to your managed organization, all the following items are moved into your Azure AD organization:

Domain name users
Subscriptions
License assignments
Internal admin takeovers are more complex and involve signing up for a Power BI account for the unmanaged organization. After you sign up, use Microsoft 365 to verify the domain name. No users or service plans migrate during an internal takeover.

Domain name verification isn't working
When you verify your domain, you update the DNS records with your domain name registrar. A period of time is required for the change to propagate through the world's DNS servers. The time taken can be an hour or more. During this period, Azure can't read the record or verify the domain name.

If the domain is still unverified after an hour, check that you've entered the correct details. You can check them directly with your registrar or by using the Resolve-DnsName PowerShell command.

## PowerShell

Copy

````Resolve-DnsName -Name proseware.com -Type TXT````
You should see something like this:

PowerShell

Copy
Name                                     Type   TTL   Section    Strings
----                                     ----   ---   -------    -------
proseware.com                            TXT    3600  Answer     {MS=ms94126796}

## A domain name is already in use
A domain name created in one Azure AD organization won't be verified in a new organization. Delete the custom domain name from the old Azure AD organization. Also delete any created users or apps that use the domain name in their app ID URI. After you delete these resources and the domain name, you can then add the custom domain name to the new Azure AD organization.

Check your knowledge
1. What should you do if domain name verification fails?

Wait up to an hour, go to the Azure Active Directory > Custom domain names pane, and select Verify again.
Wait a half hour, and refresh your browser to view the status in Azure.
x Wait at least an hour, then check that the data is correct with your domain registrar.


2. How many Azure AD organizations can use a single domain name?

None
x 1
900


## Summary
1 minute
Your company has started to use more services on Azure. As part of a new project, you proved that users find it easier to sign in with their current company-email addresses.

With Azure Active Directory (Azure AD), you can add a custom domain name. You can then create Azure users based on that domain. You saw the process of adding the domain name, verifying it, and adding users.

By reducing the number of usernames your employees must remember, you improve their productivity. You also reduce the number of support requests from employees trying to sign in to resources. When you add your custom domain name to Azure AD, employees use the current email addresses they're accustomed to.

Learn more