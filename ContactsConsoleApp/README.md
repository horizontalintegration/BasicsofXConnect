# Contacts Console App

This console application fetches the contact details like Title, First Name, Last name based on the contact identifier i.e. email address.

---

## Program.cs
Run the application and you will be asked to enter the email address of the contact. Once correctly provided, it will fetch the details of existing contact.

## Prerequisites
1. VS 2015 or higher

## How to Setup?
1. Clone this repository.
2. Open ContactsConsoleApp.sln
3. Open ./Program.cs file and make the following changes in MainAsync() method.
    3.1 Make sure you have valid Certificate Thumbprint at line number 30/31 at value provided for FindValue.
    ```csharp
        CertificateWebRequestHandlerModifierOptions options =
           CertificateWebRequestHandlerModifierOptions.Parse("StoreName=My;StoreLocation=LocalMachine;FindType=FindByThumbprint;FindValue=587d948806e57cf511b37a447a2453a02dfd3686");
    ```
    3.2 Make sure you have valid urls of the xConnect site at line number 39,40,41.
    ```csharp
   var collectionClient = new CollectionWebApiClient(new Uri("https://sc9.xconnect/odata"), clientModifiers, new[] { certificateModifier });
            var searchClient = new SearchWebApiClient(new Uri("https://sc9.xconnect/odata"), clientModifiers, new[] { certificateModifier });
            var configurationClient = new ConfigurationWebApiClient(new Uri("https://sc9.xconnect/configuration"), clientModifiers, new[] { certificateModifier });
    ```
4. Run the console application.
5. You will be asked to enter correct/existing contact's email address. Once provided it will fetch the details of that contact.
