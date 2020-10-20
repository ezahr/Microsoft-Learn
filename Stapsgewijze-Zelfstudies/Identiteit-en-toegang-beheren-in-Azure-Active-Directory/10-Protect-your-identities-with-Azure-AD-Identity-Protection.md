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

![tt](./../pictures/your_account_is_at_risk.png)

## Multifactor authentication (MFA) registration policy
Multifactor authentication adds a second layer of protection to your users' identities. With multifactor authentication, the user has to go through an additional verification step after they successfully provide their username and password.

You can use an MFA registration policy to make sure all users are registered for multifactor authentication from the first time they use their account. You also configure this policy so you can enforce sign-in risk policies. This way, you let users self-remediate after a sign-in risk is detected.

You fill in a form to configure an MFA registration policy by using the Azure portal. You'll need to provide details about which users the policy targets and whether it should be enabled or disabled.

After you configure an MFA registration policy, the user is asked to register when they sign in. The user sees this notification.


Users must complete the registration within 14 days, but they can choose to skip signing in during that period. After 14 days, they'll have to complete registration before they're allowed to sign in again.

Next unit: Investigate and remediate risks detected by Azure AD Identity Protection

![tt](./../pictures/more-information-required.png)

Next unit: Investigate and remediate risks detected by Azure AD Identity Protection

## Investigate and remediate risks detected by Azure AD Identity Protection
10 minutes
Investigations help you understand how you can improve your identity security posture, make it possible for you to respond to risks better, and help you avoid risks in the future.

In your retail company, you've configured Azure Active Directory Identity Protection policies, and risks are being detected. Your manager has asked you to investigate and remediate all the risks detected and share a report with the project manager. The team will use it to understand the company's identity-based risks better.

In this unit, you'll learn how to investigate risks by using reports. You'll see how to remediate different types of risks and deal with any user accounts that might be blocked.

## Investigate risks
Identity Protection provides reports you can use to investigate identity-based risks detected for your organization's users. These reports come in different types. Each kind of report gives the administrator information about certain risks. The administrator can then take specific actions to address those risks.    

|Report |	Information included |	Actions the admin can take	Period covered|
|Risky sign-ins|	Location details, device details, sign-ins confirmed as safe, or with dismissed or remediated risks.	Confirm that sign-ins are safe or confirm that they're compromised.	Last 30 days|
|Risky users|	Lists of users at risk and users with dismissed or remediated risks. User history of risky sign-ins.|	Reset user passwords, dismiss user risk, block user sign-ins, and confirm user accounts as compromised.	Not applicable|


You use these reports to investigate risks detected by Identity Protection. The reports help you understand how to better prevent risks and improve your security stance for identities.

You can also access risk detection type reports, which combine information about risky user detections and sign-in detections. Use these reports to see how different risk types are related and take appropriate action.

You can view and download all reports from the Azure portal.


![tt](./../pictures/You-can-view-and-download-all-reports-from-the-Azure-portal.png)


## Remediate risks
When your investigation is complete, you'll want to remediate the risks if you're not already using risk policies to automatically deal with them. Always address detected risks quickly.
There are different ways to remediate risks. The methods you use depend on your organization's needs.

## REMEDIATE RISKS

|Remediation method|	Description|
|Self-remediation|	If you configure risk policies, you can let users self-remediate. When Identity Protection has detected a risk, users either reset their password or go through multifactor authentication to unblock themselves. After self-remediation, these detected risks are considered closed. In your risk policies, the lower the acceptable risk level that triggers the policy, the more users will be affected. In general, we recommend that you set the threshold for user risk policies at high and set sign-in risk policies to medium and above.|
|Reset passwords manually	|For some organizations, automated password reset might not be an option. In this case, the administrator can manually enforce password resets. For example, the administrator can generate a temporary password and advise the user. The user can then change their password.|
|Dismiss user risk detections|	Sometimes, password reset isn't possible. For example, perhaps the affected user account was deleted. In this case, you can dismiss the risk detections for this user. If you choose to dismiss user risk detections, all associated risk detections for the user are closed.|
|Close individual detections|	All detected risks contribute to an overall risk score for a user. This risk score represents the probability that a user account is compromised. The administrator can also choose to close individual risk detections and lower the overall risk of a user's account. For example, the administrator can find out from a user that a particular risk detection is no longer needed and dismiss it. The overall risk that a user account was compromised is lowered.|

## Unblock users
User accounts can be blocked by risk policies or manually by the administrator after an investigation. How these user accounts are unblocked depends on the type of risk that caused the blockage:
Accounts blocked because of sign-in risk

An account blocked because of sign-in risk can be unblocked by excluding the user from the policy. The account might be unblocked if the administrator asks the user to sign in from a familiar location or device. Sometimes, sign-ins are blocked from unfamiliar locations or devices. There might be an alert for suspicious behavior based on what's known about the user account's sign-in patterns. The policy can also be disabled if the administrator found issues with it.

Accounts blocked because of user risk

An account might be blocked if the user was flagged because of possible risky behavior. The administrator can reset the password for the user to unblock the account. To remove the block, the administrator might dismiss the activity identified as risky or exclude the user from the policy. If the policy is causing problems for many users, the administrator can completely disable the policy.

Check your knowledge

1. Which report would you review to find devices that were identified as part of a detected risk?

Risky sign-in report
Risky user report
x Risky registration report

2. You want to use a risky sign-in report to find information on risky sign-ins for the past 29 days. How can you access this report?

X You can access and download the report from the Azure portal.
You can't access the report from the portal because the data isn't retained any longer.
You can't access the report from the portal, but only if you downloaded it in the first 30 days.



## Summary
2 minutes
You were asked to prevent your company's identities from being compromised again and ensure that identities are protected in the future. This problem is a common problem for retail companies such as yours, which must guard their reputation for trustworthiness and conform with data protection legislation.

You used Azure Active Directory Identity Protection to protect your organization's identities by detecting, investigating, and remediating risks.

Without Identity Protection, your organization's identities wouldn't be protected and could have been compromised again. Your company can now use Identity Protection to protect its identities and help prevent negative reputation and financial loss.

Learn more
To learn more about Azure Active Directory Identity Protection, see these articles:

[What is Azure Active Directory Identity Protection?](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/overview-identity-protection)
[Azure Active Directory Identity Protection - Security overview](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/concept-identity-protection-security-overview)
[What is risk?](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/concept-identity-protection-risks)