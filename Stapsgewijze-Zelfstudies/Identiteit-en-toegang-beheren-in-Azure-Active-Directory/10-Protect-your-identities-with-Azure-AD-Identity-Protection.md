## Protect your identities with Azure AD Identity Protection


[rotect your identities with Azure AD Identity Protection](https://docs.microsoft.com/en-us/learn/modules/protect-identities-with-aad-idp/)

Use the advanced detection and remediation of identity-based threats to protect your Azure Active Directory identities and applications from compromise.

Learning objectives

|In this module, you will:|
|---------------------------------------------------|
|Describe the features of Azure Active Directory Identity Protection.|
|Describe the investigation and remediation features of Azure Active Directory Identity Protection.|


Prerequisites
Basic familiarity with Azure Active Directory
This module is part of these learning paths
Manage identities and governance for Azure administrators

[2 min Introduction](https://docs.microsoft.com/en-us/learn/modules/protect-identities-with-aad-idp/1-introduction)
[10 min Azure AD Identity Protection overview](https://docs.microsoft.com/en-us/learn/modules/protect-identities-with-aad-idp/2-azure-ad-idp-overview)
[10 min Detect risks with Azure AD Identity Protection policies](https://docs.microsoft.com/en-us/learn/modules/protect-identities-with-aad-idp/3-detect-risks-with-policies)
[10 min Investigate and remediate risks detected by Azure AD Identity Protection](https://docs.microsoft.com/en-us/learn/modules/protect-identities-with-aad-idp/4-investigate-detected-risks)
[2 min Summary](https://docs.microsoft.com/en-us/learn/modules/protect-identities-with-aad-idp/5-summary)



## Introduction
2 minutes
Azure Active Directory (Azure AD) Identity Protection gives you advanced detection and remediation of identity-based risks to protect your Azure AD identities and applications.

You work for a retail organization that has its identities stored in Azure AD. There have been several recent incidents where identities were compromised. It's possible that sensitive customer information was exposed. You'd like to use Azure native services to protect your company from any future incidents. You've decided to use Identity Protection to protect your identity infrastructure.

In this module, you'll explore what Identity Protection is and how to use it. You'll detect risks by using risk policies. Then you'll investigate detected risks and remediate them.

By the end of this module, you'll know how to protect your organization's identities from identity-based risks by using Identity Protection.

Your company's specialist expertise is in retail, not in identity protection. It wants to continue to focus on its areas of strength, but still ensure that it's protected against identity risks. Your organization can use Identity Protection to automate the detection, investigation, and remediation of risks related to users' identities without hiring expensive security experts.



## Azure AD Identity Protection overview
10 minutes
Azure Active Directory (Azure AD) Identity Protection helps you to automatically detect, remediate, and investigate identity-based risks for your organization.

The retail company you work for is conscious about its reputation. Compromised identities have previously enabled malicious users to obtain customer information fraudulently. These attacks have affected your organization's reputation, and ultimately its profitability. Your manager has asked you to investigate Identity Protection as a solution. You've been asked to report back on what the service does and how it's used.

In this unit, you'll learn what Identity Protection is and the risks involved in using it. You'll explore the different workflows you can use in Identity Protection to protect your identities.


![tt](./../pictures/What-is-Azure-Active-Directory-Identity-Protection.png)

## What are risks?  kasns maal schade. 
Risks can be described as suspicious activity and actions by users when they sign in or when they take actions after signing in. That's why risks are categorized in two ways, as user risks and sign-in risks.

## User risk
A user risk is caused when a user's identity or account is compromised. User risks can include

|Risk|	Description|
|------------|-----------------------------------|
|Unusual behavior|	The account showed unusual activity or the patterns of usage are similar to those patterns that Microsoft systems and experts have identified as attacks.|
|Leaked credentials|	The user's credentials could have been leaked. For example, Microsoft might have found a list of leaked credentials on the dark web, which could affect your user accounts.|

Sign-in risk
Here, Identity Protection scrutinizes each authentication request to judge whether it was authorized by the owner of the identity. Sign-in risks can include:

## SIGN-IN RISK
|Risk|	Description|
|Unfamiliar sign-in properties|	Identity Protection remembers and learns a particular user's sign-in history. For example, when a sign-in occurs from a location that's unusual for the user, a risk detection is triggered.
Atypical travel	For example, when two or more sign-ins occur from distant locations in an unrealistically short time period, a risk detection is raised.|
|Malware-linked IP address	| For example, if the IP address where the sign-in originates is known to have been in contact with an active bot server, a risk detection is raised.|
|Anonymous IP address|	For example, a sign-in originates from an anonymous IP address. Because these details can be used by attackers to hide their real IP address or location, a risk detection is raised.|

## Azure Active Directory Identity Protection workflow
There are two different ways to detect and handle identity risks:

Self-remediation workflow

Identity Protection uses risk policies to automatically respond to detected threats for you. You configure a risk policy to decide how you want Identity Protection to respond to a particular type of risk. You then choose the action the user is asked to complete. The action could be a self-service password reset or multifactor authentication enforcement. Using policies in this way helps save time and gives you peace of mind.

In this workflow, the administrator first configures the risk policies that then monitor for identity risks. When a risk is detected, the policies enforce measures to remediate it. A policy might, for example, ask a user to reset their password in response to a risk detected. The user then resets their password, and the risk is remediated.


![tt](./../pictures/Administrator-remediation-workflow.png)

Check your knowledge
1. How do you protect against identity-based risks by using Azure AD Identity Protection?

Configure an investigation policy and then remediate.
Configure a report, remediate, and then configure a policy.
x configure a policy, investigate by using a report, and remediate.

2. You want to analyze risks that describe authentication requests for sign-ins that probably weren't authorized by users. 

Which type of risks will you analyze?
User risk
x Sign-in risk
Authentication risk


Detect risks with Azure AD Identity Protection policies
10 minutes
Risk policies make it possible for your organization to respond more appropriately to identity risk.

Previously, your retail company's IT team didn't have security skills in-house and had to hire external contractors to protect identities. Your manager wants to avoid the same situation going forward. Your company needs to be able to respond to threats in a controlled and more cost-effective manner, without weakening security.

You've been asked to investigate how identity risks are detected in Azure Active Directory Identity Protection. You've been asked to look into risk policies and how to use them.

In this unit, you'll investigate what risk policies are. You'll also learn what each type of risk policy is used for and how to configure and enable them. Then you'll see what the end-user experience is like for each risk policy type.

What is a risk policy?
You configure a risk policy to decide how you want Identity Protection to respond to a particular type of risk. Do you want to block or allow access? Do you want to make users go through additional authentication before you allow access? Risk policies help you respond to risks rapidly. Your company can leverage risk policies and avoid hiring external contractors to handle identity-based risks.

Different risk policies are available based on the type of identity risk. You can use a sign-in risk policy or a user risk policy.

## Sign-in risk policy
A sign-in risk policy scrutinizes every sign-in and gives it a risk score. This score indicates the probability that the sign-in was attempted by the person whose credentials are used. You decide which level of risk is acceptable by choosing a threshold of low, medium, or high. Based on the risk level, you choose whether to allow access, automatically block, or allow access only after additional requirements are met. For example, users might be asked to go through multifactor authentication to remediate detected risks that are considered to be at the medium level. Users could be blocked entirely if the risk is considered high.

You use a form to configure a sign-in risk policy in the Azure portal. You specify settings such as:

The users this policy should target.
The conditions that must be met, such as how high a score triggers the policy.
How you want to respond.
Make sure users are already registered for Azure Multi-Factor Authentication before you apply this policy.



![tt](./../pictures/Make-sure-users-are-already-registered-for-Azure-Multi-Factor-Authentication-before-you-apply-this-policy.png)


After a sign-in risk is identified, the user is asked to take action to remediate the risk. They're told what triggered the risk and what they need to provide to resolve the issue. For example, the user might see this notification.


![tt](./../pictures/help_us_to_protect_your_account.png)


## User risk policy
Here, Identity Protection learns the user's normal behavioral patterns. Identity Protection then uses this knowledge to calculate the likely risk that the user's identity was compromised. Based on this risk, the administrator can decide whether to allow access, block it, or allow access only after additional requirements are met. The user could, for example, be asked to change their password by using self-service password reset before they're allowed access.

You use a form to configure a user risk policy in the Azure portal. You specify settings such as the users this policy should target, the conditions that must be met, and how you'll respond. Make sure users are already registered for self-service password reset before you apply this policy.


![tt](./../pictures/configure-a-user-risk-policy-in-the-Azure-portal.png)

After a user risk is identified, the user is asked to take action to remediate that risk. They're told what triggered the risk and what they need to provide to resolve the issue. For example, the user might see this notification.

![tt](./../picturesyour_account_is_at_risk.png)

## Multifactor authentication (MFA) registration policy
Multifactor authentication adds a second layer of protection to your users' identities. With multifactor authentication, the user has to go through an additional verification step after they successfully provide their username and password.

You can use an MFA registration policy to make sure all users are registered for multifactor authentication from the first time they use their account. You also configure this policy so you can enforce sign-in risk policies. This way, you let users self-remediate after a sign-in risk is detected.

You fill in a form to configure an MFA registration policy by using the Azure portal. You'll need to provide details about which users the policy targets and whether it should be enabled or disabled.

