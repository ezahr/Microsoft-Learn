## 8 Allow users to reset their password with Azure Active Directory self-service password reset
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
