# MANAGING YOUR COLLECTION'S SETTINGS

## How to configure your account

### Change your account information

Step 1: Login to your Uwazi instance.

Step 2: Navigate to the **Settings** area and click **Accounts**.

Step 3: You can change your email address here, as well as your account password.

![](images/image_1.png)

### Recover your password

Step 1: At the login screen, click **Forgot Password?**.

Step 2: You will receive an email from the [no-reply@uwazi.io](mailto:no-reply@uwazi.io) account. Follow the instructions.

- If you cannot find this recovery email, please check if it has been filtered into your ‘’Spam’’ folder.

- To reinforce your account’s security, we recommend that you use unique and long passwords (a-Z, 0-9, &%).

Watch a [screencast](https://drive.google.com/open?id=1fJcdhGPGRZEZMn6ExzS2csinH3FJwcBd).

### Enable two-factor authentication

To add an extra layer of security to your Uwazi instance:

Step 1: Login to your Uwazi instance.

Step 2: Navigate to the **Settings** area and click **Accounts**.

Step 3: You will see **Two-step verification**, click on **Protect your Account**.

Step 4: Open [Authy](https://authy.com/features/setup/) or [Google Authenticator](https://support.google.com/accounts/answer/1066447?co=GENIE.Platform%3DAndroid&hl=en) and generate your verification code.

Step 5: Enter the code and click **Confirm**.

- If you have successfully enabled two-factor authentication, your account settings will reflect this.

![](images/image_2.png)

Watch a [screencast](https://drive.google.com/open?id=1G02gKDvIejl4NxwpyiIqiIU5KPjbamBE).

### Login with two-factor authentication

Step 1: Login to Uwazi with your credentials.

Step 2: You will be prompted to input your authentication code. Enter the code from Authy or Google Authenticator.

- If the code is approved, you will be logged in.

Watch a [screencast](https://drive.google.com/open?id=1lYbJHkDrDoAeYzoVcPcYQPoAWyUf3JmR).

FAQs related to two-factor authentication

- Google Authenticator: [https://support.google.com/accounts/answer/185834?hl=en](https://support.google.com/accounts/answer/185834?hl=en)

- Authy application: [https://authy.com/help/](https://authy.com/help/)

## How to create, edit and delete users

### Understanding user permissions

If you work in a team or in collaboration with other people, Uwazi allows administrators to create new users with specific permissions to help you update your collection. Uwazi currently supports three different kinds of roles:

- **Admin**: The admin role has the ability to create, see and edit all entities; change all settings throughout the Uwazi instance; and add new users
- **Editor**: The editor role has the ability to create, see and edit all entities
- **Collaborator**: The collaborator role has the ability to create new entities and can be invited to see and edit other entities on an entity by entity basis

![](images/image_3.png)

### Add new users to your instance

Step 1: Only an Admin can create new users. Navigate to the **Settings** area and click **Users**.

Step 2: You will see a list of all the current users who have access to your collection.

Step 3: You can create new users by clicking the green **Add user** button at the bottom. Here, you can also edit or delete users, as necessary.

Step 4: Enter a **username**, their **email address** and select a role (**Admin**, **Editor** or **Collaborator**) for them.

Step 5: Once this information is entered, click the green **Save** button and an email will be sent to that person with a link that allows them to set their own password.

### Create new user groups

Step 1: Only an Admin can create new users. Navigate to the **Settings** area and click **Users**.

Step 2: On the Users tab, you will see a list of all the current users who have access to your collection. Switch to the Groups tab.

Step 3: You can create new groups by clicking the green **Add Group** button at the bottom. Here, you can also edit or delete users in that group, as necessary.

Step 4: Assign a **Name of the group** and add the usernames that you want to include.

Step 5: Once this information is entered, click the green **Create Group** button.

## How to configure your collection’s general  settings

You can control various basic aspects of your Uwazi instance by navigating to the **Settings** area, then clicking on **Collection** in the left sidebar. If you make any changes, please ensure that you click **Save**. 

### Change the name of your collection

The name is "Uwazi" by default, but you can change it to anything you like. 

- [Watch a screencast](https://drive.google.com/open?id=1_6ele0a2bmdSbLD1-UjUfSd53JaUL54T).

### Customise the favicon

A favicon is the icon representing your Uwazi collection that appears in browser tabs or in bookmarks. If you want to replace the Uwazi icon for your own:

Step 1: Convert your image into .ico (icon) format. To do so, you can search the internet for an .ico converter. Save the resulting file on your local drive. 

Step 2: On the left sidebar under **Tools**, click on **Uploads**. Select **Browse files to upload** and upload the image that you converted to the .ico format. Once your image uploads, copy the URL. (It will begin with ```/assets```.) 

Step 3: Navigate back to the **Collection** settings. Under **Custom favicon**, toggle the option on and paste the above URL. 

Step 4: Click **Save**, and be sure to reload the webpage after updating your favicon.

### Set your landing page

The landing page is the first thing visitors will see when they arrive at your Uwazi instance. By default, the landing page is set to the full Library ![](images/image_0.png) without any filters applied.

However, you can set any page from within your Uwazi instance to act as the landing page instead. Toggle on the option to **Use custom landing page** and paste the relative URL in the box. A relative URL starts with a slash ```/``` and skips the domain name. For example: 

  - A page: **```/page/dicxg0oagy3xgr7ixef80k9```**
  - A Library query: **```/library/?searchTerm=test```**
  - A document or entity: **```/document/4y9i99fadjp833di/entity/9htbkgpkyy7j5rk9```**

### Customise the default Library view 

All of the entities in an Uwazi collection can be viewed on demand as cards, in a table or on a map (as long as entities have an associated geolocation). Based on your preference, you can choose to set a default view.

### Change the date format

You may change the date format, based on your preference.

### Make your collection private (or public)

If you are handling sensitive information or you just want your collection to be accessible only via login, you can toggle on the option to make the instance private.

By activating this option, your information will not be crawled by search engines, and visitors will be prompted with a login screen when trying to access your entities.

### Show cookies policy on your site

Cookies are bits of information used by some websites you visit and stored on your computer’s hard drive. Uwazi uses cookies to deliver an optimal experience for users and visitors alikes. If you would like to display a notification about the use of cookies upon first visit to your instance, toggle on the option to **Show cookie policy**. 

### Support non-Latin characters in property names

Toggling on the option of **Non-Latin characters support** will enhance support for non-Latin languages as default languages, specifically in the names of properties within your templates. This option triggers an automatic update of all properties, a process that could take several minutes and will likely change the URLs of library filters. If you have menus or links using such URLs, you will need to update them manually afterward.

- If you are not facing issues with your template property names, we recommend leaving this unchecked.

## How to track your collection’s web analytics

If you want to track analytics related to the web traffic that visits your collection, Uwazi supports both Google Analytics and Matomo. 

Step 1: Find your unique ID.
  
  - FAQ on how to set up a [Google Analytics ID](https://support.google.com/analytics/answer/3123666?hl=en) to track website visits.
  
  - If you are hosting your Uwazi instance with HURIDOCS, we provide [Matomo Analytics](https://matomo.org/) as part of the hosting. Please contact us to activate your account.

Step 2: Navigate to the **Settings** area and click on **Collection** in the left sidebar. 

Step 3: Toggle on the option for Google Analytics or Matomo Analytics, depending on your preference, and add the unique ID. 

Step 4: Click the green **Save** button.

## How to configure your collections contact and submission forms

### Mailer configuration

This allows you to configure your own SMTP or any other mail server. Uwazi instances hosted by HURIDOCS have the mail system already configured.

- This is a JSON configuration object that should match the options values required by Nodemailer, as explained [here](http://nodemailer.com/smtp/).

- This setting takes precedence over all other mailer configuration. If left blank, then the configuration file in /api/config/mailer.js will be used.

### Contact form configuration

If you have added a contact form to a page within your Uwazi instance, you must set the email address that receives the information from that form. (Learn more about how to add a contact form to your instance.)

Step 1: Navigate to the **Settings** area and click on **Collection** in the left sidebar. 

Step 2: Toggle on the option of **Contact form** and set the **Receiving email** address. 

Step 3: You can also set a different address as the **Sending email**. This email address will appear as the sender of emails associated with the contact form. If no email address is set, no-reply@uwazi.io will be used.   

Step 4: Click the green **Save** button.

### Submission form configuration 

If you have added an intake or submission form to a page within your Uwazi instance, it must be configured to work properly. (Learn more about how to add an intake or submission form to your instance.)

Step 1: Navigate to the **Settings** area and click on **Collection** in the left sidebar.

Step 2: Toggle on the option of **Public endpoints**.

Step 3: Select the template(s) that need to be whitelisted.

Step 4: In the case that submissions should be sent to a different Uwazi instance than the one where the form is found, add the URL of that destination instance.

Step 5: Click the green **Save** button.

## How to customize your collection's map configurations

### Map starting point 

Step 1: Navigate to the **Settings** area and click on **Collection** in the left sidebar. 

Step 2: To set your own default geolocation, drag the map and click to select the destination, or enter the latitude and longitude, if known.

Step 3: Click the green **Save** button.

### Maptiler key

A default key is provided with Uwazi, but you are free to swap it for your own. 

Step 1: Navigate to the **Settings** area and click on **Collection** in the left sidebar. 

Step 2: Input the MapTiler API key in the space provided. 

Step 3: Click the green **Save** button.
