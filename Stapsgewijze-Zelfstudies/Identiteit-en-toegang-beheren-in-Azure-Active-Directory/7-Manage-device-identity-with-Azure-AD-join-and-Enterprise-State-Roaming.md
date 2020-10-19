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

Why use SSPR?
In Azure AD, any user can change their password if they're already signed in. But if they're not signed in and forgot their password or it's expired, they'll need to reset their password. With SSPR, users can reset their passwords in a web browser or from a Windows sign-in screen to regain access to Azure, Microsoft 365, and any other application that uses Azure AD for authentication.

SSPR reduces the load on administrators, because users can fix password problems themselves, without having to call the help desk. Also, it minimizes the productivity impact of a forgotten or expired password. Users don't have to wait until an administrator is available to reset their password.

How SSPR works
The user initiates a password reset either by going directly to the password reset portal or by selecting the Can't access your account link on a sign-in page. The reset portal takes these steps:

Localization: The portal checks the browser's locale setting and renders the SSPR page in the appropriate language.
Verification: The user enters their username and passes a captcha to ensure that it's a user and not a bot.
Authentication: The user enters the required data to authenticate their identity. They might, for example, enter a code or answer security questions.
Password reset: If the user passes the authentication tests, they can enter a new password and confirm it.
Notification: A message is usually sent to the user to confirm the reset.
There are several ways you can customize the SSPR user experience. For example, you can add your company logo to the sign-in page so users know that they're in the right place to reset their password.

Authenticate a password reset
It's critical to verify the identity of a user before you allow a password reset. Malicious users might exploit any weakness in the system to impersonate that user. Azure supports six different ways to authenticate reset requests.

As an administrator, you choose the methods to use when you configure SSPR. Enable two or more of these methods so that users can choose the ones that they can use easily. The methods are:

AUTHENTICATE A PASSWORD RESET
Authentication method	How to register	How to authenticate for a password reset
Mobile app notification	Install the Microsoft Authenticator app on your mobile device, and then register it on the multifactor authentication setup page.	Azure sends a notification to the app, which you can either verify or deny.
Mobile app code	This method also uses the Authenticator app, and you install and register it in the same way.	Enter the code from the app.
Email	Provide an email address that's external to Azure and Microsoft 365.	Azure sends a code to the address, which you enter in the reset wizard.
Mobile phone	Provide a mobile phone number.	Azure sends a code to the phone in an SMS message, which you enter in the reset wizard. Or, you can choose to get an automated call.
Office phone	Provide a nonmobile phone number.	You receive an automated call to this number and press #.
Security questions	Select questions such as "In what city was your mother born?" and save responses to them.	Answer the questions.
In free and trial Azure AD organizations, phone call options aren't supported.

Require the minimum number of authentication methods
You can specify the minimum number of methods that the user must set up: one or two. For example, you might enable the mobile app code, email, office phone, and security questions methods and specify a minimum of two methods. Then users can choose the two methods they prefer, like mobile app code and email.

For the security question method, you can specify a minimum number of questions that the user must set up to register for this method. You also can specify a minimum number of questions that they must answer correctly to reset their password.

After your users register the required information for the minimum number of methods you've specified, they're considered registered for SSPR.

Recommendations
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

When they've registered at least the number of methods that you've required to reset a password.

When they've set up the minimum number of security questions.
2. When you enable SSPR for your Azure AD organization...

Users can change their password when they're signed in.

Admins can reset their password by using one authentication method.

Users can reset their passwords when they can't sign in.