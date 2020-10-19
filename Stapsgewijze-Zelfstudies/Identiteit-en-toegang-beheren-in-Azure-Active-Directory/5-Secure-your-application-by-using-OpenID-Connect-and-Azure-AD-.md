## 5 Secure your application by using OpenID Connect and Azure AD 


[Secure your application by using OpenID Connect and Azure AD](https://docs.microsoft.com/en-us/learn/modules/secure-app-with-oidc-and-azure-ad/)

50 min
Module
6 Units
Intermediate
Solutions Architect
Developer
Security Engineer
Azure
Azure Active Directory
Use OpenID Connect in your application to allow users to securely sign in with Azure AD identities.

Learning objectives
In this module, you will:

Understand the authentication needs of your application
Create an Azure AD tenant and configure application registration for your application
Deploy an application that uses OpenID Connect to authenticate users

Prerequisites
Basic knowledge of C#
Basic knowledge of Azure AD
This module is part of these learning paths
Manage identity and access in Azure Active Directory

|duur|Secure your application by using OpenID Connect and Azure AD|
|5 min |Introduction|
|10 min|Modern authentication for your application|
|10 min|Create an Azure AD tenant and configure registration for your application|
|10 min|Exercise - Create an Azure AD tenant and configure registration for your application|
|10 min|Exercise - Deploy an application that uses OpenID Connect to authenticate users|
|5 min|Summary|

## Introduction
5 minutes
Organizations are often challenged to build secure applications while minimizing complexity for users. How would you give users secure access to an application to help them do their jobs, without requiring them to remember a new username, password, or other credentials?
Let's assume you work for a transportation company. You're building an application that allows drivers to sign in and manage their schedules. You want to allow users to sign in with their Azure Active Directory (Azure AD) accounts that they currently use for Microsoft 365 so they don't have to create additional accounts. You will configure your application to allow authentication with OpenID Connect and Azure AD.
Learn how OpenID Connect enables users to authenticate with a single account to multiple applications.

## Learning objectives
In this module, you will:

Understand the authentication needs of your application.
Create an Azure AD tenant and configure application registration for your application.
Deploy an application that uses OpenID Connect and Azure AD to authenticate users.
Prerequisites
Basic knowledge of C#
Basic knowledge of Azure AD
Next unit: Modern authentication for your application

Modern authentication for your application
10 minutes
There are many options for securing identities in your application. Selecting the right technology for your application will help ensure that your application is secure, while maintaining a great experience for your users.

At your transportation company, your drivers have identities in Microsoft 365. You want to understand how you can use those identities to authenticate them in your scheduling app. You want to provide secure access to your application without requiring the drivers to manage extra user accounts and credentials.

Let's look at the standards and services that you can use for authentication.

## What is Azure Active Directory?
Azure Active Directory (Azure AD) is Microsoft's cloud-based identity and access management service. It simplifies authentication for developers by providing identity as a service. It supports industry-standard protocols such as OAuth 2.0 and OpenID Connect. Azure AD allows users to sign in and view resources. And it has features to help secure your identities, such as Identity Protection and multi-factor authentication. Microsoft services such as Azure and Microsoft 365 use Azure AD to store and manage users. Whenever Microsoft 365 needs to verify a user, for example, Azure AD performs all identity and access management.


## Authentication in Azure Active Directory
Users authenticate in two stages:

The identity provider verifies the identity of users who exist in the directory. Upon successful authentication, tokens are issued that contain information related to the successful authentication.
The user passes those tokens to the application. The application must validate the user’s security tokens to ensure that authentication was successful.
Let’s consider a basic scenario where identity is required: a user in a web browser needs to authenticate to a web application. Consider the following diagram for this scenario:



After this process of authentication, in which the user is positively identified, the web application must authorize the user's access to resources. Authorization is the process by which the web application checks whether the user is permitted to access the requested resource.



![tt])(./../pictures/Authentication-in-Azure-Active-Directory.png)

This communication flow is built upon the industry-standard protocols of OAuth 2.0 and OpenID Connect.

## OAuth 2.0
OAuth 2.0 is the industry-standard protocol for authorization. It provides specific authorization flows for web, desktop, and mobile applications. This specification was primarily designed to enable users to authorize an application to access data in another application.

Imagine you have an application that stores contact information. You want to allow users with LinkedIn accounts to import their LinkedIn contact information into your application. With OAuth, you can enable this server-to-server communication. Users can authorize your application to access contact information, without needing to share passwords between applications.

OAuth works well for authorization of server-to-server communications, but it doesn't include standards or specifications for authentication. As applications continued to grow their sharing of data and account information between them, the need for a standard framework for single-sign on became evident. This led to the development of OpenID Connect.

## OpenID Connect
OpenID Connect is an authentication layer that's built on top of OAuth 2.0. It includes identity verification methods that are missing from OAuth 2.0. OpenID Connect gives you an access token plus an ID token, which you can send to an application to prove your identity.

The ID token is a JSON Web Token (JWT) and contains information about the authenticated user. The identity provider signs the token, so that applications can verify the authentication by using the provider's public key.

JSON Web Token is an open international standard that defines how applications can exchange data securely as digitally signed messages. The content of each token is not encrypted, but the message is signed with the private key of the identity provider. By checking the signature with the corresponding public key, applications can prove that the token is issued by the identity provider and has not been tampered with.

![tt](./../pictures/microsoft_identify_platform.png)

This diagram shows how the client application, the application server, and the identity provider communicate in an OpenID Connect authentication request. The client might be a mobile app or a desktop application. In this case, it's a web browser. The application server is usually a web server that hosts webpages or a web API. The identity provider in the middle is Azure AD.

When the web browser goes to the web application, the web server needs the user to be authenticated. It redirects the browser to Azure AD and provides its own client ID, which has been registered in Azure AD. When the user has successfully authenticated against Azure AD, the provider redirects the browser to the URI on the web server.

When you implement OpenID Connect, you must obtain a client ID for your application by creating an application registration in Azure AD. You then copy the client ID into the application's configuration files. In the application registration, you will also include the URI of the web application so that Azure AD can redirect the client successfull

Modern authentication for your application
1. Which sentence correctly describes OpenID Connect?

x OpenID Connect is an authentication standard.
OpenID Connect is an authorization standard.
OpenID Connect is an identity provider.

2. You want users of your application to authenticate by using their accounts, which are stored in Microsoft 365. What must you 
do in Azure AD?

Register every Microsoft 365 user account in Azure AD.
x register the application in Azure AD.
Add the users to a single security group and register the group in Azure AD.

3. In which of the following scenarios would OpenID Connect be the best option?

x Securing your sign-in page
Connecting to a database
When you aren't concerned about security or reliability


Create an Azure AD tenant and configure registration for your application
10 minutes
Suppose you have decided to use OpenID Connect with your transportation company's app to allow users to authenticate by using the same credentials they use to access Microsoft 365. These credentials are stored in Azure Active Directory (Azure AD). Let's look at the resources and configuration you'll need to set this up properly.

Create an Azure AD tenant
A tenant is an instance of Azure AD that represents an organization. It's a dedicated instance of Azure AD that an organization or app developer receives when the organization or app developer creates a relationship with Microsoft, like signing up for Azure, Microsoft Intune, or Microsoft 365.

Each Azure AD tenant is distinct and separate from other Azure AD tenants. An Azure AD tenant has its own representation of work and school identities, and app registrations. An app registration inside your tenant can allow authentication from accounts only within your tenant or across all tenants.

Azure AD tenants are created in the .onmicrosoft.com domain by default. You can't delete or change this name, but you can add your own registered domain name, and then create users and app registrations within that domain.

Azure AD tenants can be created only in the Azure portal.

Register a web app
Within the Azure AD tenant, you'll need a registration for the application. The registration is a record of security details for the application in Azure AD. A registration ensures that Azure AD can identify the application and the user. An app registration includes these details:

Name. This value identifies the registration and application.
Application type. Use the Web app/API type for websites or web APIs that are accessed through the HTTP protocol. Use the Native type for applications that are installed on a user's device or computer.
Sign-on URL. This value is the location of the sign-on page in the published application.
Application ID. This generated GUID is unique to the registration. Configure your application to send the same GUID to Azure AD whenever it authenticates a user.
Application registrations are configured in the Azure portal. Applications are registered on the App registrations > New application registration page for the Azure AD tenant.

Configure the app for authentication
There's a lot of detail to ensure that the OpenID Connect protocol specifications are followed properly. To help developers use OpenID Connect in their applications, Microsoft provides middleware to facilitate this communication. This middleware consists of APIs that include methods and properties that make it easy to interact with the identity provider.

The middleware is available for several different platforms. Microsoft supplies and supports middleware libraries for .NET Framework, .NET Core, and Node.js. There are also client-side libraries for JavaScript, Angular, PHP, and other platforms.

For example, if you have an ASP.NET Core 2.X web app, and you need to use the OpenID Connect protocol to authenticate users using Azure AD, you can utilize the Microsoft.AspNetCore.Authentication.AzureAD.UI NuGet package. Then, add the following values to the appsettings.json file:

ida:Tenant. This configuration value is the identity of the Azure AD directory that contains the application registration.
ida:ClientId. This configuration value is the GUID that uniquely identifies the client registration.
Then, configure the authentication middleware in the Startup.ConfigureServices method:

C#
````
Copy
services.Configure<CookiePolicyOptions>(options =>
    {
        options.CheckConsentNeeded = context => true;
        options.MinimumSameSitePolicy = SameSiteMode.None;
    });

services.AddAuthentication(AzureADDefaults.AuthenticationScheme)
    .AddAzureAD(options => Configuration.Bind("AzureAd", options));

services.Configure<OpenIdConnectOptions>(AzureADDefaults.OpenIdScheme, options =>
    {
        options.Authority = options.Authority + "/v2.0/";
        options.TokenValidationParameters.ValidateIssuer = false;
    });

````

You can use the authentication middleware to sign in users from a one or more Azure AD tenants. The middleware is initialized in the Startup.Auth.cs file, by passing it the client ID of the application and the URL of the Azure AD tenant where the application is registered. The middleware then takes care of:

## Downloading the Azure AD metadata.
Processing OpenID Connect authentication responses.
Integration with the session cookie.
Next unit: Exercise - Create an Azure AD tenant and configure registration for your application


## Azure Cloud Shell

This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox.

xercise - Create an Azure AD tenant and configure registration for your application
10 minutes
This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox.
Due to the impact of the global health pandemic, Azure resources are being prioritized towards health and safety organizations. You may experience some issues when you deploy resources used in the exercises. Please try again or choose a different region. For more information, see Azure blog post - Update #3: Business continuity with Azure.

To use Azure Active Directory (Azure AD) as an authentication provider for your application, you must register that application in Azure AD. Suppose you want to use Azure AD as the authentication provider for your scheduling application. You have an ASP.NET Core web app, and you want to configure Azure AD as the identity provider.

Here, you'll create and configure an application registration.

Create an Azure AD tenant
To start, you'll use the Azure portal to create a new Azure AD tenant.

Go to the Azure portal .

On the Azure portal menu or from the Home page, select Create a resource.

Select the Identity category, and then select Azure Active Directory.


Azure Cloud Shell

This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox.

authenticate users
10 minutes
This module requires a sandbox to complete. A sandbox gives you access to Azure resources. Your Azure subscription will not be charged. The sandbox may only be used to complete training on Microsoft Learn. Use for any other reason is prohibited, and may result in permanent loss of access to the sandbox.
Due to the impact of the global health pandemic, Azure resources are being prioritized towards health and safety organizations. You may experience some issues when you deploy resources used in the exercises. Please try again or choose a different region. For more information, see Azure blog post - Update #3: Business continuity with Azure.

You can use the Azure CLI to deploy and test an application that uses OpenID Connect.

You previously registered the application in Azure Active Directory (Azure AD). You can now deploy and run the application and see if the authentication works.

In this exercise, you'll configure an application to authenticate users against your Azure AD tenant and deploy the web app.

Configure and deploy the application that uses OpenID Connect to authenticate users
Run the following command in Azure Cloud Shell to clone the repo that contains the source for our app.

````
git clone https://github.com/MicrosoftDocs/mslearn-secure-app-with-oidc-and-azure-ad.git
````

````
cd ~/mslearn-secure-app-with-oidc-and-azure-ad/app/
````

````
code appsettings.json
````



````
{
  "AzureAd": {
    "Instance": "https://login.microsoftonline.com/",
    "Domain": "<domain-name>.onmicrosoft.com",
    "TenantId": "<TenantID-GUID>",
    "ClientId": "<ClientID-GUID>",
    "CallbackPath": "/signin-oidc"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*"
}

````


Select Ctrl+S to save the file and Ctrl+Q to close the code editor.

Run the following command to build and deploy the initial web app.

Azure CLI

Copy
az webapp up \
    --resource-group [Sandbox resource group] \
    --location centralus \
    --sku F1 \
    --name educationapp-$RANDOM
Copy the URL from the command output. You'll need this address to configure the app registration.

Configure the app registration
Now let's configure the app registration to authorize the URL of the web service:

In the Azure portal , select your user name in the upper-right corner, and then select Switch directory. Choose the Learn Module AAD Tenant directory that you created earlier. Sign in if you're prompted.

In the left pane, select Azure Active Directory.

Under Manage, select App registrations. Then select the WebApp-OpenIDConnect-DotNet registration that you created in the previous exercise.

Select Authentication.

Paste the URL from the Cloud Shell output in the previous section into the Redirect URIs area, and append the suffix /signin-oidc. Ensure that the URL uses HTTPS.

Delete the redirect URI https://localhost:5000/signin-oidc.

Paste the same URL into the Logout URL field, and append the suffix /signout-oidc.

Under Implicit grant, select ID tokens.

Select Save.

## https://aad.portal.azure.com/#@boschpeteroutlook.onmicrosoft.com/dashboard/private/31d09266-3ccf-4378-943b-c4973e8b0019


![tt](./../pictures/Secure-your-application-by-using-OpenID-Connect-and-Azure-AD1.png)

![tt](./../pictures/ictures/Secure-your-application-by-using-OpenID-Connect-and-Azure-AD2.png)

![tt](./../pictures/pictures/Secure-your-application-by-using-OpenID-Connect-and-Azure-AD3.png)

!![tt](./../pictures/pictures/Secure-your-application-by-using-OpenID-Connect-and-Azure-AD4.png)


## Test the application
Open a new browser window and go to the web application's base URL.

When you're prompted, sign in. You'll be authenticated against your Azure AD tenant. The web app also requests some permissions, and you'll be prompted for your consent.


![tt](./../pictures/Youll be-authenticated-against-your-Azure-AD-tenant.png)

Select Accept. The web app then appears. The title bar includes your authenticated username, indicating that you've been successfully logged in with the identity in the Learn Module AAD Tenant directory.

You've now created both the application registration and the web app itself. You've configured these objects with the information that they need to locate each other.

Now that the web app is configured to authenticate against Azure AD, you can use that directory to manage all the user accounts that can access your application. The same accounts that grant users access to services like Microsoft 365 can now be used to access your app. Users have to remember only one set of credentials for both systems. Administrators have less work to do because each user has only one account.

Next unit: Summary


Summary
5 minutes
In this module, you have explored the OpenID Connect concepts for authentication.

By using an example application, you used the OpenID Connect ASP.NET OWIN middleware to sign in users from a single Azure Active Directory (Azure AD) tenant. Users now sign in with the same accounts that they use for Microsoft 365.

Clean up
The sandbox will clean up your resources automatically when you finish this module. But the Azure AD tenant that you created must be deleted manually.

To delete the Azure AD tenant, follow these steps:

In the Azure portal , in the top bar, select your account, and then select Switch directory.
Select the Learn Module AAD Tenant directory that you created in unit 4.
In the left pane, select Azure Active Directory, select App Registrations, and then select the WebApp-OpenIDConnect-DotNet registration.
Select Delete, and then select Yes.
In the left pane, select Azure Active Directory. Then under Manage, select Properties.
Under Access management for Azure resources, select Yes, and then select Save.
In the upper right of the portal, select your user account, and then select Sign out.
Sign in with your normal credentials. In the top bar, select your account, and then select Switch directory.
Select the Learn Module AAD Tenant directory that you created in unit 4.
In the left pane, select Azure Active Directory, select Delete directory, and then select Delete.
In the upper right of the portal, select your user account, and then select Sign out.
Further reading

[Authorize access to web applications by using OpenID Connect and Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/azuread-dev/v1-protocols-openid-connect-code)
[OpenID Connect specification](https://openid.net/specs/openid-connect-core-1_0.html)
[ID tokens](https://docs.microsoft.com/en-us/azure/active-directory/develop/id-tokens)
[Azure Active Directory access tokens](https://docs.microsoft.com/en-us/azure/active-directory/develop/access-tokens)


[De soeverein is niet thuis](http://zuidugchelen.eu:82/s/9bfRNonCAYFpF5Q)

[](http://zuidugchelen.eu:82/s/9bfRNonCAYFpF5Q)

