# Managing Your Collection’s Settings

## How to configure your account

### Change your account information

Step 1: Log into your instance.

:::{attention}
Add your username, which is not the same as your registered email address.
:::

Step 2: Navigate to the **Settings** ![Settings icon](images/cog-solid.png) area and click **Account**.

Step 3: You can change your email address here, as well as your account password.

### Recover your password

Step 1: At the login screen, click **Forgot Password?**.

Step 2: You will receive an email from the `uwazi@uwazi.uwazi.io` account. Follow the instructions.

:::{attention}
If you cannot find this recovery email, check if it has been filtered into your Spam folder.
:::

:::{tip}
To reinforce your account’s security, we recommend that you use unique and long passwords (a-Z, 0-9, &%).
:::

### Enable two-factor authentication

To add an extra layer of security to your Uwazi instance:

Step 1: Log into your instance.

Step 2: Navigate to the **Settings** ![Settings icon](images/cog-solid.png) area and click **Account**.

Step 3: You will see **Two-Factor Authentication**, click on **Enable**.

Step 4: Open [Authy](https://authy.com/features/setup/) or [Google Authenticator](https://support.google.com/accounts/answer/1066447?co=GENIE.Platform%3DAndroid&hl=en) and generate your verification code.

Step 5: Enter the code and click **Enable**. If you have successfully enabled two-factor authentication, your account settings will reflect this.

### Login with two-factor authentication

Step 1: Log into your instance with your credentials.

Step 2: You will be prompted to input your authentication code. Enter the code from Authy or Google Authenticator. If the code is approved, you will be logged in.

- [FAQs related to Google Authenticator](https://support.google.com/accounts/answer/185834?hl=en)

- [FAQs related to Authy](https://authy.com/help/)

## How to create, edit and delete users

### Understanding user permissions

If you work in a team or in collaboration with other people, Uwazi allows administrators to create new users with specific permissions to help you update your collection. Uwazi currently supports three different kinds of roles:

- **admin** role has the ability to create, see and edit all **Entities**; change all settings throughout the Uwazi instance; and add new users
- **editor** role has the ability to create, see and edit all **Entities**
- **collaborator** role has the ability to create new **Entities** and can be invited to see and edit other on an individual basis

### Add new users to your collection

Step 1: Only an **admin** can create new users. Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click **Users & Groups**.

Step 2: You will see a list of all the current users who have access to your collection. Here, you can also edit or delete users, as necessary.

Step 3: You can create new users by clicking the **Add user** button at the bottom.

Step 4: Enter a username, their email address and select a role (**admin**, **editor** or **collaborator**) for them.

Step 5: Once this information is entered, click the **Save** button and an email will be sent to that person with a link that allows them to set their own password.

### Create new user groups

Step 1: Only an **admin** can create new users. Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click **Users & Groups**.

Step 2: On the **Users** tab, you will see a list of all the current users who have access to your collection. Switch to the **Groups** tab.

Step 3: You can create new groups by clicking the **Add group** button at the bottom. Here, you can also edit or delete users in that group, as necessary.

Step 4: Assign a Name for the new group and add the usernames that you want to include as members for the group.

Step 5: Once this information is entered, click the **Save** button.

## How to configure your collection’s general settings

You can control various basic aspects of your instance by navigating to the **Settings** area ![Settings icon](images/cog-solid.png), then clicking on **Collection** in the left sidebar. If you make any changes, please ensure that you click **Save**.

### Change the name of your collection

The name default **Collection Name** is "Uwazi", but you can change it to anything you like.

### Customise the favicon

A favicon is the icon representing your Uwazi collection that appears in browser tabs or in bookmarks. If you want to replace the Uwazi icon for your own:

Step 1: Convert your image into .ico (icon) format. To do so, you can search the internet for an .ico converter. Save the resulting file on your local drive.

Step 2: On the left sidebar under **Tools**, click on **Uploads**. Then **Import asset** and upload the image that you converted to the .ico format. Once your image uploads, copy the URL. It will begin with `/assets`.

Step 3: Navigate back to **Collection**. Paste the previously copied URL into the field **Custom Favicon**.

Step 4: Click **Save**, and be sure to reload the webpage after updating your favicon.

### Set your landing page

The landing page is the first thing visitors will see when they arrive at your Uwazi instance. By default, the landing page is set to the full **Library** ![Library icon](images/image_0.png) without any **Filters** applied.

However, you can set any page from within your Uwazi instance to act as the landing page instead. Paste the relative URL in the field **Custom landing page**. A relative URL starts with a slash `/` and skips the domain name. For example:

- A **Page**: ```/page/dicxg0oagy3xgr7ixef80k9```

- A **Library** query: ```/library/?searchTerm=test```

- An **Entity**: ```/entity/9htbkgpkyy7j5rk9```

### Customise the default Library view

All of the **Entities** in your collection live in the **Library** ![Library](images/image_0.png) and can be viewed on demand as cards, in a table or on a map (as long as entities have an associated geolocation). Based on your preference, you can choose to set a default view. [Learn more about organising and exploring](organising-your-collection.md) your collection.

### Change the format of date-entry fields

To change the format that is used to enter dates in form fields, select one of the following supported date formats:

- YYYY/MM/DD (Year/Month/Day)
- DD/MM/YYYY (Day/Month/Year)
- MM/DD/YYYY (Month/Day/Year)
- YYYY-MM-DD (Year-Month-Day)
- DD-MM-YYYY (Day-Month-Year)
- MM-DD-YYYY (Month-Day-Year)

:::{note}
This change will be reflected only when entering data. The format that is used to display dates depends on the language you have selected to display the user interface of Uwazi.
:::

### Make your collection public (or private)

Your collection is by default private. This means that your information will not be crawled by search engines, and visitors will be prompted with a login screen when trying to access any part of your collection: the Library, individual Entities, the landing page, etc. If you are handling sensitive information or you just want your collection to be accessible only to users with login credentials, keep the default setting. If you want to make your collection public and accessible to anyone, activate the option **Public instance**. You can always turn your collection back to private by disabling this option.

### Show cookies policy on your site

Cookies are bits of information used by some websites you visit and stored on your computer’s hard drive. Uwazi uses cookies to deliver an optimal experience for users and visitors alike. If you would like to display a notification about the use of cookies upon first visit to your instance, activate the option to **Show cookie policy**.

### Support for non-Latin characters in the names of properties

Older instances of Uwazi have an option called **Non-Latin Characters Support**. It enhances support for non-Latin languages as default languages, specifically in the names of **Properties** within **Templates**. Toggling on this option triggers an automatic update of all properties, a process that could take several minutes and will likely change the URLs of **Filters** in the **Library** ![Libray icon](images/image_0.png). Menus or links that use such URLs will need to be updated manually afterward.

:::{tip}
If you are not facing issues with your template property names, we recommend leaving this option alone.
:::

:::{note}
If you do not see this option available in the **Settings** area ![Settings icon](images/cog-solid.png) under **Collection**, it is because support for non-Latin characters is activated in newer instances of Uwazi by default, so you do not need to take any action.
:::

## How to track your collection’s web analytics

If you want to track analytics related to the web traffic that visits your collection, Uwazi supports both Google Analytics and Matomo.

Step 1: Find your unique ID.
  
:::{seealso}
FAQ on how to set up a [Google Analytics ID](https://support.google.com/analytics/answer/3123666?hl=en) to track website visits.
:::
  
:::{note}
If you are hosting your Uwazi instance with HURIDOCS, we provide [Matomo Analytics](https://matomo.org/) as part of the hosting. [Contact us](how-to-report-bugs-or-problems-in-uwazi.md) to activate your account.
:::

Step 2: Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click on **Collection** in the left sidebar.

Step 3: Add your Google Analytics or Matomo Analytic unique ID to the corresponding field and click the **Save** button.

## How to configure a Contact Form or Submission Form

### Mailer configuration

If your instance is hosted by HURIDOCS, then your mail system is already configured. If you are hosting an instance on your own server, then you can configure your own SMTP or any other mail server.

- This is a JSON configuration object that should match the options values required by [Nodemailer](http://nodemailer.com/smtp/).

- This setting takes precedence over all other mailer configuration. If left blank, then the configuration file in `/api/config/mailer.js` will be used.

### Contact form configuration

If you have added a **Contact Form** to a custom **Page** within your collection, you must set the email address that receives the information from that form. [Learn more about adding Pages](designing-your-website.md#how-to-add-pages-to-your-collection) to your collection.

Step 1: Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click on **Collection** in the left sidebar.

Step 2: Provide in the field **Contact form email** an email address that will receive the form's submissions.

Step 3: You can also set a different address as the **Sending Email**. This email address will appear as the sender of emails associated with the contact form. If no email address is set, `no-reply@uwazi.io` will be used.

Step 4: Click the **Save** button.

### Submission form configuration

If you have added an **Intake or Submission Form** to a custom **Page** within your collection, it must be configured to work properly. [Learn more about adding Pages](designing-your-website.md#how-to-add-pages-to-your-collection) to your collection.

Step 1: Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click on **Collection** in the left sidebar.

Step 2: Toggle on the option of **Public Endpoints**.

Step 3: Select the **Template(s)** that need to be whitelisted.

Step 4: In the case that submissions should be sent to a different Uwazi instance than the one where the form is found, add the URL of that destination instance.

Step 5: Click the **Save** button.

## How to customise your collection's map configurations

### Map provider

Uwazi uses Mapbox as the default map provider. However, you have the option to choose Google Maps as your map provider instead.

:::{note}
Changing the map provider for a collection requires a personal API key.
:::

Step 1: Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click on **Collection** in the left sidebar.

Step 2: Under **Map**, you can change the map provider for your collection.

Step 3: A default API key for the online map service is provided with Uwazi, but you can swap it for your own API key. Input the map API key in the space provided.

:::{seealso}
[Detailed guidelines](https://developers.google.com/maps/documentation/javascript/get-api-key) on how to set up a Google Maps API key.
:::

Step 4: Click the **Save** button.

### Map starting point

Step 1: Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click on **Collection** in the left sidebar.

Step 2: To set your own default geolocation, drag the map and click to select the destination, or enter the latitude and longitude, if known.

Step 3: Click the **Save** button.

## How to view your collection’s storage and other stats

Step 1: Navigate to the **Settings** area ![Settings icon](images/cog-solid.png) and click on **Dashboard** in the left sidebar.

Step 2: In the **Dashboard**, you will see figures related to the following:

- How many total user accounts your collection has

- How many types of users (Admins, Editors, Collaborators) your collection has

- How many entities your collection has across all languages

- How many files (Primary Documents, Supporting Files, Custom Uploads) your collection has

- How much storage space your collection is currently using
