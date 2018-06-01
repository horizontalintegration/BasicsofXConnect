# Basics of xConnect

This repository contains code to create,update and fetch the contacts from  sitecore, asp.net webform and console application through xConnect.

---

## Projects
This repository contains three projects:

1. **ContactsConsoleApp:** a console application
2. **KioskContact:** a .net web form application
3. **XConnect.Demo.Contacts.Web:** a sitecore website with Sitecore Package xConnect Demo Sitecore-1.0.0.0.zip

## ContactsConsoleApp
This console application asks you the id (email address) of the contact and once provided the correct id, this application fetches the details of the contacts.

## KioskContact
This is a simple .net web-form application. Run the **kioskcontact.aspx**page to open the form. Fill up the form, Capture the image and click on "Create" button.
It will create/update contact based on provided information and set the captured image as the contact's avtar.

## XConnect.Demo.Contacts.Web
This is a sitecore site having one item/page **CreateContact**. You can access the page/item by appending **/CreateContact** in your website root. 
f.g. http://sc9.sc/**createcontact**.  
The sitecore items are available in the sitecore package **xConnect Demo Sitecore-1.0.0.0.zip**.
