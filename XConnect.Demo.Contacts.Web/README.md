# XConnect.Demo.Contacts.Web

Consider this application as a Sitecore web mvc application. A page item **createContact** will create the contact on the form submission.

---

## /createContact
This item has the controller rendering which calls the action method **CreateContacts** of **Page** Controller. The Post method of **CreateContacts** calls the *RegisterContact* method which register/create the Contact/Experience profile.

## Prerequisites
1. VS 2015 or higher
2. Sitecore 9.0 initial release or higher

## How to Setup?
1. Make sure you have a plain Sitecore 9.0 or higher version instance is up and running
2. Clone this repository.
3. Open XConnect.Demo.Contacts.Web.sln
4. Open ./Controllers/PageController.cs file and make the following changes in RegisterContact() method.
    4.1 Make sure, you have updated the goal and channel id according to your sitecore items.
    4.2 Make sure you have valid Certificate Thumbprint at line number 71 at value provided for FindValue.
    ```csharp
         CertificateWebRequestHandlerModifierOptions options =
               CertificateWebRequestHandlerModifierOptions.Parse("StoreName=My;StoreLocation=LocalMachine;FindType=FindByThumbprint;FindValue=587d948806e57cf511b37a447a2453a02dfd3686");
    ```
    4.3 Make sure you have valid urls of the xConnect site at line number 81,82,83.
    ```csharp
   var collectionClient = new CollectionWebApiClient(new Uri("https://sc9.xconnect/odata"), clientModifiers, new[] { certificateModifier });
            var searchClient = new SearchWebApiClient(new Uri("https://sc9.xconnect/odata"), clientModifiers, new[] { certificateModifier });
            var configurationClient = new ConfigurationWebApiClient(new Uri("https://sc9.xconnect/configuration"), clientModifiers, new[] { certificateModifier });
    ```
5. Modify *XConnect.Demo.Contacts.Web/XConnect.Demo.Contacts.Web/Properties/PublishProfiles/FolderProfile.pubxml* file as per local environment. Recommended Path is the Sietcore 9.0 webroot folder.
6. Perform the Visual Studio Publish
7. Install Sitecore Package avaialble at https://github.com/horizontalintegration/BasicsofXConnect/blob/master/Sitecore%20Packages/xConnect%20Demo%20Sitecore-1.0.0.0.zip
8. After installing the package, Publish following items:
    7.1 */sitecore/layout/Layouts/ViewLayout*
    7.2 */sitecore/layout/Renderings/CreateContact*
    7.3 */sitecore/templates/User Defined*  - with Subitems
    7.4 */sitecore/content/Home/CreateContact*
9. Run http://YOUR-SITECORE-WEBSITE-DOMAIN/createContact

