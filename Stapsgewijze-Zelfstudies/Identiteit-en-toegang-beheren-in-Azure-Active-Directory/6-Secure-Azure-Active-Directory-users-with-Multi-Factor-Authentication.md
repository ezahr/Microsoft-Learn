## 6 Secure Azure Active Directory users with Multi-Factor Authentication


[Secure Azure Active Directory users with Multi-Factor Authentication](https://docs.microsoft.com/en-us/learn/modules/secure-aad-users-with-mfa/)

38 min Module 6 Units Beginner

Security Engineer
Administrator
Azure
Azure Portal
Azure Active Directory
Learn how to use multi-factor authentication with Azure AD to harden your user accounts.

Learning objectives
In this module, you will:

Learn about Azure Multi-Factor Authentication (MFA)
Create a plan to deploy Azure MFA
Turn on Azure MFA for users and specific apps

Prerequisites
Basic knowledge of the Azure portal
Basic knowledge of Azure Active Directory
This module is part of these learning paths
Manage identity and access in Azure Active Directory
Manage identities and governance for Azure administrators

|3 min|Introduction|
|10 min|What is Azure Multi-Factor Authentication?|
|7 min|Plan your multi-factor authentication deployment|
|8 min|Exercise - Enable Azure Multi-Factor Authentication|
|6 min|Configure multi-factor authentication methods|
|4 min|Summary|

Introduction
3 minutes
Imagine you are security engineer for a large manufacturing firm. Your company works on several big contracts for popular personal electronics companies including Microsoft. Clients send you their confidential designs which are then stored in your Azure infrastructure. Plenty of hackers would love to get their hands on the next generation designs and it's your job to protect them.

You've done a lot of work hardening your network and ensuring that only the right people have access to client data, but there's still a big hole to protect - user accounts. This module will look at one of the best ways to stop unauthorized users from gaining access through a username/password - multi-factor authentication.

Learning objectives

|In this module, you will:Learn about Azure Multi-Factor Authentication (MFA)|
|------------------------------------------------|
|Create a plan to deploy Azure MFA|
|Turn on Azure MFA for users and specific appsPrerequisites|
|Basic knowledge of the Azure portal|
|Basic knowledge of Azure Active Directory|
|Next unit: What is Azure Multi-Factor Authentication?|

What is Azure Multi-Factor Authentication?
10 minutes
Protecting your cloud assets is one of the primary goals for security group. One of the primary ways unauthorized users get access to systems is by obtaining a valid username/password combination. Azure can help mitigate this with several features of Azure Active Directory including:

Password complexity rules. This will force users to generate hard(er)-to-guess passwords.

Password expiration rules. You can force users to change their passwords on a periodic basis (and avoid using previous-used passwords).

Self-service password reset (SSPR). This allows users to self-serve and reset their password if they have forgotten it without involving an IT department.

Azure AD Identity Protection. To help protect your organization's identities, you can configure risk-based policies that automatically respond to risky behaviors. These policies can either automatically block the behaviors or initiate remediation, including requiring password changes.

Azure AD password protection. You can block commonly used and compromised passwords via a globally banned-password list.

Azure AD smart lockout. Smart lockout helps lock out malicious hackers who are trying to guess your users’ passwords or use brute-force methods to get in. It recognizes sign-ins coming from valid users and treats them differently than the ones of malicious hackers and other unknown sources.

Azure AD Application Proxy. You can provision security-enhanced remote access to on-premises web applications.

Single sign-on (SSO) access to your applications. This includes thousands of pre-integrated SaaS apps.

Azure AD Connect. Create and manage a single identity for each user across your hybrid enterprise, keeping users, groups, and devices in sync.

These are all great options which deter someone guessing or brute-forcing a password. However, sometimes passwords are obtained through social engineering, or poor physical security practices (like putting your password on a sticky note under your keyboard!). In these cases, the above features won't stop an intrusion. Instead, security administrators will want to turn to Azure Multi-Factor Authentication (MFA).

What is Azure MFA?
Azure Multi-Factor Authentication (MFA) supplies added security for your identities by requiring two or more elements for full authentication.

These elements fall into three categories:

Something you know - which might be a password or the answer to a security question.
Something you possess - which might be a mobile app that receives a notification or a token-generating device.
Something you are - which typically is a biometric property, such as a fingerprint or face scan used on many mobile devices.




![tt](./../pictures/what_is_azure_azure_multifacture_atuhentification.png)

Using Azure MFA increases identity security by limiting the impact of credential exposure. To fully authenticate, a malicious hacker who has a user's password would also need their phone or their fingerprint. Authentication with only a single factor is insufficient, and without authentication from Azure MFA, a malicious hacker is unable to use those credentials to authenticate. You should enable Azure MFA wherever possible, because it adds enormous benefits to security.

Azure MFA is the Microsoft two-step verification solution. Azure MFA helps safeguard access to data and applications while meeting user demand for a simple sign-in process. It delivers strong authentication via a range of verification methods, including phone call, text message, or mobile app verification. The security of Azure MFA lies in its layered approach. Compromising multiple authentication factors presents a significant challenge for malicious hackers. Even if a malicious hacker manages to learn the user's password, it is useless without also possessing the trusted device. If the user loses the device, a person who finds it won't be able to use it without the user's password.

## How Multi-Factor Authentication works
Here’s what happens when someone tries to connect to a resource that’s security enhanced by Azure MFA, and the service is on-premises:

![tt](./../pictures/How-Multi-Factor-Authentication-works.png)

Azure MFA allows the provider of the request service to validate that users are real people and not bots, that they have their devices with them, and that they can provide any additional information.

Azure MFA improves security for the requesting users, because someone can’t easily impersonate them. You should require Azure MFA on all services, especially on mobile services.

## How to get Multi-Factor Authentication?
Multi-Factor Authentication comes as part of the following offerings:

Azure Active Directory Premium or Microsoft 365 Business - Both of these offerings support Azure Multi-Factor Authentication using Conditional Access policies to require multi-factor authentication.

Azure AD Free or standalone Microsoft 365 licenses - Use pre-created Conditional Access baseline protection policies to require multi-factor authentication for your users and administrators.

Azure Active Directory Global Administrators - A subset of Azure Multi-Factor Authentication capabilities are available as a means to protect global administrator accounts.

Next unit: Plan your multi-factor authentication deployment

Plan your multi-factor authentication deployment
7 minutes
Before starting a deployment of Azure Multi-Factor Authentication, there are several things you should decide.

First, consider rolling out MFA in waves. Start with a small group of pilot users to evaluate the complexity of your environment and identify any setup issues or unsupported apps or devices. Then broaden that group over time and evaluating the results with each pass until your entire company is enrolled.

Next, make sure to create a full communication plan. Azure MFA has several user interaction requirements including a registration process. Keep users informed every step of the way and let them know what they are required to do, important dates, and how to get answers to questions if they have trouble. Microsoft provides communication templates including posters, and email templates to help draft your communications.

Azure MF policies
Azure Multi-factor Authentication is enforced with Conditional Access policies. Conditional Access policies are IF-THEN statements. IF a user wants to access a resource, THEN they must complete an action. For example, a payroll manager wants to access the payroll application and is required to perform multi-factor authentication to access it. Other common access requests that might require MFA include:

IF a specific cloud application is accessed
IF a user is accessing a specific network
IF a user is accessing a specific client application
IF a user is registering a new device
Deciding supported authentication methods
When you turn on Azure MFA, you can choose the authentication methods you want to make available. You should always support more than one method so users have a backup option in case their primary method is unavailable. You can choose from the following methods:

DECIDING SUPPORTED AUTHENTICATION METHODS

|Method|	Description|
|--------------------|-----------------------------------------------|
|Call to a phone|	Azure can call a supplied phone number. The user then approves the authentication using the keypad. This is a preferred backup method.|
|Text message to a phone	|A text message with a verification code can be sent to a mobile phone. The user then enters the verification code into the sign-in interface to complete the authentication.Administrators can enable one or more of the options above and then users can opt-in to each support authentication method they want to use.|
|Selecting an authentication method|Finally, you must decide how users will register their selected methods. The easiest approach is to use Azure Active Directory Identity Protection. If your organization has licenses for Identity Protection, you can configure it to prompt users to register for MFA the next time they sign in.|

Users can also be prompted to register for MFA when they try to use an application or service that requires multi-factor authentication. Finally, you can enforce registration using a Conditional Access policy applied to an Azure group containing all users in your organization. This approach requires some manual work to periodically review the group to remove registered users. There are some useful scripts in the documentation to automate some of this process.

Next unit: Exercise - Enable Azure Multi-Factor Authentication

Exercise - Enable Azure Multi-Factor Authentication
8 minutes
Configure Azure MFA for applications
Let's walk through the basic steps necessary to configure and enable Azure Multi-Factory Authentication using Conditional policies. Keep in mind that a real deployment requires significant thought and planning. Make sure you review the documentation links at the end of this module before you enable MFA for your environments.

 Important

Azure AD Premium is need for this exercise. You can use a 30-day free trial to try this feature out, or just read through the instructions below to understand the flow.

Configure Multi-Factor Authentication options
Sign in to the Azure portal using a Global administrator account.

Navigate to the Azure Active Directory dashboard using the Azure Active Directory option in the sidebar.

Select MFA under the Security group. Here you will find options for Multi-Factor authentication.

![tt](./../pictures/mfa_gettingstarted.png)

Select the Additional cloud-based MFA settings link under Configure. A new browser page will open, where you can see all the MFA options for Azure.


![tt](./../pictures/mfa_gettingstarted2.png)


This is where you would select the supported authentication methods, in the screen above, all of them are selected.

You can also enable or disable app passwords here, which allow users to create unique account passwords for apps that don't support multi-factor authentication. This feature lets the user authenticate with their Azure AD identity using a different password specific to that app.

## Setup conditional access rules for MFA
Next let's examine how to set up Conditional Access policy rules that would enforce MFA for guest users accessing specific apps on your network.

Switch back to the Azure portal and select Azure Active Directory > Security > Conditional access.

Select New policy from the top menu.


![tt](./../pictures/mfa_gettingstarted3.png)


Name your policy, for example "All guests"

Select Users and groups to open the panel.

Select Select users and groups
Check the All guest and external users checkbox to apply this to all guests
Select Done to close the panel.
Select Cloud apps or actions.

Select Select apps and press the Select group
Choose an app where you want to enable Azure MFA such as Visual Studio App Center
Select Select and then Done to close the panel.
Review the Conditions section.

Select Locations and then configure it for Any location.
Under Access Controls select Grant and make sure that Grant access is selected, select the Require multi-factor authentication check box - this is what enforces MFA.

Select Select to close the window.

Set Enable policy to On.

Select Create to create the policy.

![tt](./../pictures/mfa_gettingstarted4.png)

MFA is now enabled for your selected application(s). The next time a guest tries to sign into that app they will be prompted to register for MFA.

## Configure Azure MFA for passwords
Finally, let's look at how to configure MFA for user accounts. This is another way to get to the multi-factor auth settings.

Navigate back to the Azure Active Directory dashboard in the Azure portal.

Select Users.

At the top of the Users pane, select Multi-Factor Authentication.
![tt](./../pictures/mfa_gettingstarted4.png)

Next unit: Configure multi-factor authentication methods


## Configure multi-factor authentication methods
6 minutes
As mentioned earlier, it's recommended that administrators enable users to be able to select more than one authentication method in case their primary method is unavailable.

When a user signs into a service that requires MFA the first time, they will be asked to register their preferred multi-factor authentication method as shown in the following screenshot.


Configure-multi-factor-authentication-methods


 Tip

If you followed the previous exercise and turned on MFA for an account and app, then you can try accessing that app with the given user account and you should see the above flow.

Once they've registered, each time they sign into a service or app that requires MFA the Azure login process will prompt for the additional authentication information as shown in the following image.

## Azure Authentication Methods
As we saw earlier, there are several possible authentication methods that an administrator can set up. Some of these also support Self-Service Password Reset (SSPR) which allows users to reset their password by supplying a secondary form of authentication. You can couple this service with Azure MFA to ease the burden on IT staff.

The following table lists the authentication methods and the services that can use them.

|nr|Authentication method|	Services|
|----|-----------------------------|------------------------------|
|1|Password|	Azure MFA and SSPR|
|2|Security questions|	SSPR|
|3|Email address|	SSPR|
|4|Microsoft Authenticator app|	Azure MFA and SSPR|
|5|OATH hardware token|	Azure MFA and SSPR|
|6|Text message|	Azure MFA and SSPR|
|7|Voice call|	Azure MFA and SSPR|
|8|App passwords	|Azure MFA in certain cases|



Let's explore these in a bit more detail.

## Password
This is the only method that you can’t disable.

## Security questions
This method is available only for non-administrative accounts that use Self-Service Password Reset.

|Azure stores security questions privately and in a security-enhanced manner on a user object in the directory. Only users can answer the questions and only during registration. An administrator can’t read or change a user’s questions or answers.|
|Azure provides 35 predefined questions, all translated and localized based on the browser locale.|
|You can customize the questions by using the administrative interface; however, Azure displays them in the language entered. The maximum length is 200 characters.|

## Email address
This method is available only in SSPR. It's recommended that you avoid the use of an email account that doesn’t require the user’s Azure AD password to access it.

## Microsoft Authenticator app
This method is available for Android and iOS. Users can register their mobile app at https://aka.ms/mfasetup

|The Microsoft Authenticator app helps prevent unauthorized access to accounts and helps stop fraudulent transactions by pushing a notification to your smartphone or tablet. Users view the notification and, if it’s legitimate, select Verify. Otherwise, they select Deny.|
|Users can use the Microsoft Authenticator app or a third-party app as a software token to generate an OATH verification code. After entering the username and password, the users enter the code provided by the app on the sign-in screen. The verification code provides a second form of authentication.|

## OATH hardware tokens
OATH is an open standard that specifies how to generate one-time password codes. Azure AD supports the use of OATH-TOTP SHA-1 tokens of the 30-second or 60-second variety. Customers can get these tokens from the vendor of their choice. Note that secret keys are limited to 128 characters, which might not be compatible with all tokens.

## Text message
Azure sends a verification code to a mobile phone using SMS. The user must enter the code into the browser within a specific time period to continue.

## Voice call
Azure uses an automated voice system to call the number and the owner uses the keypad to confirm the authentication. Note that this option is not available to the free/trial Azure AD tier.

## App password
Certain non-browser apps don’t support Azure MFA. If users are enabled for Azure MFA and try to use non-browser apps, they’ll be unable to authenticate. The app password allows users to continue to authenticate.

## Monitoring adoption
Azure AD includes a Usage & insights view in the Monitoring section where you can monitor the authentication methods activity. From here you can view the adoption of MFA and SSPR:



![tt](./../pictures/Monitoring-adoption.png)

In addition to the overall registration numbers, you can also see the success and failure of registrations per authentication method. This allows you to understand which authentication methods your users most commonly registered and which ones are easy for them to register. This data is calculated using the last 30 days of audit logs from the combined security info registration and SSPR registration experiences.

You can drill down and see the latest registration audit information for each user by clicking the chart.


You can also learn more about SSPR usage in your organization through the Usage tab on the main view as shown in the following image.

![tt](./../pictures/SSPR-registration-experiences.png)



![tt](./../pictures/SSPR-registration-experiences.png)



Check your knowledge
1. Which of the following authentication methods is not available for MFA?

Text message
Microsoft Authenticator app
x Security questions Correct. Security questions can only be used with Self-Service Password Reset.

2. Which of the following authentication methods cannot be disabled?

Text message
x Password Correct. Passwords are always usable as an authentication method and cannot be disabled.
Microsoft Authenticator app
3. True or False. You must activate multi-factor authentication for all users in the directory you enable it in.

True
x False
Correct. MFA can be enabled for a subset of your users; this is actually a recommendation - start small to ensure you don't lock someone out of your systems.


1 out of 3 questions is incorrect. Please correct question 1.
Next unit: Summary


## Summary
4 minutes
Using Azure Multi-Factor Authentication, you can ensure that when users sign in to access your confidential systems and data, they are who they say they are. Azure AD allows you to create policies to ensure that specific apps are protected, while allowing more public systems to remain easier to get to. In addition, you can leverage other services such as Azure AD Identity Protection and Azure Smart Lockout to fully protect your identity surface area.

Further reading
To learn more about some of the topics we've examined in this module, check out the following links to documentation.


[What is Azure Active Directory Identity Protection?}(https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/overview-identity-protection)
[Planning a cloud-based Azure Multi-Factor Authentication deployment}(https://docs.microsoft.com/en-us/azure/active-directory/authentication/howto-mfa-getstarted)
[Deploy Azure AD self-service password reset}(https://docs.microsoft.com/en-us/azure/active-directory/authentication/howto-sspr-deployment)


## Explore other modules

Manage identity and access in Azure Active Directory
Manage identities and governance for Azure administrators

