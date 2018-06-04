# Kiosk Contact

This is a webform based .net application independent of Sitecore. Sitecore.xConnect dll references has been added to connect this application to xConnect.

---

## /KioskContact.aspx & .cs
This page will create/update the contacts on the form submission. Method **createUpdateContactDemo** creates and updates the contact/expereince profile based on provided email address.

## Prerequisites
1. VS 2015 or higher
2. Machine having webcam/external camera connected - not compulsory but if you want to set avtaar by taking picture, a webcam in needed.

## How to Setup?
1. Clone this repository.
2. Open KioskContact.sln
3. Open ./KioskContact.aspx.cs file and make the following changes in createUpdateContactDemo() method.
	3.1 Make sure, you have updated the goal and channel id according to your sitecore items.
    3.2 Make sure you have valid Certificate Thumbprint at line number 62 at value provided for FindValue.
    ```csharp
         CertificateWebRequestHandlerModifierOptions options =
               CertificateWebRequestHandlerModifierOptions.Parse("StoreName=My;StoreLocation=LocalMachine;FindType=FindByThumbprint;FindValue=587d948806e57cf511b37a447a2453a02dfd3686");
    ```
    3.3 Make sure you have valid urls of the xConnect site at line number 72,73,74.
    ```csharp
   var collectionClient = new CollectionWebApiClient(new Uri("https://sc9.xconnect/odata"), clientModifiers, new[] { certificateModifier });
            var searchClient = new SearchWebApiClient(new Uri("https://sc9.xconnect/odata"), clientModifiers, new[] { certificateModifier });
            var configurationClient = new ConfigurationWebApiClient(new Uri("https://sc9.xconnect/configuration"), clientModifiers, new[] { certificateModifier });
    ```
4. Modify *KioskContact/KioskContact/Properties/PublishProfiles/FolderProfile.pubxml* file as per local environment. 
5. Perform the Visual Studio Publish
6. Make the host entry of the domain name.
7. Run http://YOUR-WEBSITE-DOMAIN/kioskcontact.aspx in your favourite browser.