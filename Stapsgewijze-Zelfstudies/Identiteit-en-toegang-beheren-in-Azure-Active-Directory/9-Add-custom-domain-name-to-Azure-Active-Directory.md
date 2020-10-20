## 9 Add custom domain name to Azure Active Directory


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