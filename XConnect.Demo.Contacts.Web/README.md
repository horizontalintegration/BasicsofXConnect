# XConnect.Demo.Contacts.Web

Consider this application as a Sitecore web mvc application. A page item **createContact** will create the contact on the form submission.

---

## /createContact
This item has the controller rendering which calls the action method **CreateContacts** of **Page** Controller. The Post method of **CreateContacts** calls the *RegisterContact* method which register/create the Contact/Experience profile.