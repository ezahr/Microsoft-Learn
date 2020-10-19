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

