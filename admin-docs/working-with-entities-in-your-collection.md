# WORKING WITH ENTITIES IN YOUR COLLECTION 

## Understanding view and edit permissions for entities

An Uwazi collection is made up of types of information called **Entities** that live in the **Library** ![](images/image_0.png). An entity has **Properties**, can hold **Primary Documents** and/or **Supporting Files**, and can have **Relationships** to other entities. Some examples of entities might include a court, a case, a specific person, a report or an event. 

In the **Library**, an entity can be viewed as a card, in a table or on a map (as long as it has an associated geolocation), and can also be filtered according to its **Properties**. [Learn more about how to organise and explore your collection](https://uwazi.readthedocs.io/en/latest/admin-docs/organising-your-collection.html).

By default, the visibility of newly created entities is **Restricted**. In practice, this means that only the user who created an entity as well as all users with **Admin** or **Editor** permissions can see and edit it. 

In order to make an entity visible to everyone who has access to your Uwazi collection, you must click the entity’s **Share** button and explicitly share it with the **Public**. (Keep in mind that if your entire Uwazi collection is configured to be private, **Public** in this case strictly refers to everyone who possesses login credentials. [Learn more about configuring the accessibility of your collection](#).)

For users with login credentials to an Uwazi collection, there are two sets of blue filters that help quickly sort through the visibility settings of different entities. The first set refers to the visibility of all of the entities on a global level: 
- **Restricted**, meaning that only a selected subset of users are able to see and/or edit the entity
- **Published**, meaning that everyone with access to the collection is able to see the entity

The second set of filters indicates which particular entities have been explicitly shared with your individual user account or with a specific user group to which you belong: 
- **Shared as Viewer**, meaning your individual user account or a specific user group to which you belong has been given permission to see the entity
- **Shared as Editor**, meaning your individual user account or a specific user group to which you belong has been given permission to edit the entity

## How to add new entities to the Library

Remember, before you can create a new entity, make sure you have already created a corresponding template. [Learn more about how to create templates](#). 

To create a new entity:

Step 1: Click on the **Library** icon ![](images/image_0.png) in the top navigation menu. 

Step 2: On the bottom right hand side of the screen, click on the **Create entity** button.

Step 3: Select which template to use from the list, give the entity a name and fill in any of the properties that you want to include. (You may always come back to add, edit or delete this information later.)

Step 4: Click the **Save** button once you have finished.

Step 5: If the entity is intended to feature any PDFs (**Primary Document**), click the **Upload PDF** button in the right sidebar and select the desired PDF(s) from within the file browser. 

If the entity is intended to feature any other attached materials (**Supporting Files**), click the **Add Supporting File** button and select the desired file(s) from within the file browser. 

Step 6: Decide who should be able to see and edit the entity. By default, the new entity is only visible to you and other users with **Admin** or **Editor** permissions. To change these settings, click on the **Share** button in the right sidebar. 

Add any new users (individuals or groups) who should have access to the entity, choose if they should be able to see and/or edit the entity, and click **Save changes**. Remember, if you’d like the entity to be available to everyone who has access to your Uwazi collection, make sure to share it with the **Public**.

## How to directly add PDFs to the Library

Uwazi particularly supports the management of collections of documents in PDF format. Numerous functions can be carried out when a PDF is uploaded as a **Primary Document** within an entity, such as conducting full text search, creating a clickable table of contents, creating text references, and more.

If many of the entities in your collection feature "primary" PDF documents, it could become tedious to create entity after entity, giving them a title and filling in any properties, and only after they are saved, finally adding a PDF.

For situations such as these, Uwazi makes it possible to upload PDF(s) directly into the Library as a first step without the prior creation of an entity:

Step 1: Click on the **Library** icon ![](images/image_0.png) in the top navigation menu. 

Step 2: On the bottom right side of the screen, click on the **Upload PDF(s) to Create** button.

Step 3: Select the desired PDF(s) from within the file browser. (To select more than one file, hold down the CTRL key or the Command key before clicking.)

Step 4: Once uploaded, the PDF will appear attached to a new entity in the **Library** with a **Name** property that is automatically filled in with the PDF file's name. 

Step 5: You can edit the name of the entity by automatically pulling out the content in the PDF file. Click on the **View** button in the right sidebar to view your file, and click on the **Edit** button. Within the document, use the cursor to highlight the text that you want to have as the name of the entity. **Click to fill**, written in blue, will appear in the sidebar. Click on **Click to fill**, and the highlighted text will appear as the name. You can also edit other aspects of the entity in the sidebar. Make sure to save any changes you make.

Step 6: Decide who should be able to see and edit the entity. By default, the new entity is only visible to you and other users with **Admin** or **Editor** permissions. To change these settings, click on the **Share** button in the right sidebar.

Add any new users (individuals or groups) who should have access to the entity, choose if they should be able to see and/or edit the entity, and click **Save changes**. Remember, if you’d like the entity to be available to everyone who has access to your Uwazi collection, make sure to share it with the **Public**.

## How to add entities in bulk with CSV import

It may be that you have a large pre-existing collection of data points or materials that you want to add to your Uwazi collection. Doing so one by one would be a tedious task, so for situations such as these, Uwazi makes it possible to upload in bulk by preparing and then importing a **Comma-Separated Values (CSV) file**.

### Import entities without documents or supporting files

Remember, before you can import entities in bulk, make sure you have already created a corresponding template. [Learn more about how to create templates](#).

Step 1: Create a **CSV file** on your computer. It should include a column for each of the properties that are included on the entity’s template. Import works by matching property names – therefore, be meticulous in using the same column labels in the CSV file as the property names on the template in Uwazi. As well, be sure to follow these guidelines:

- Property names are not case sensitive, which means you can use either lowercase, capitals or a combination of both.
- The first column should be called “Title” and is required in your CSV file. This is where you will put the **Name** property of each entity.
- There is no need to include the **Date Added** property because it is filled automatically during the import into Uwazi.
- If you have a **Geolocation** property, its corresponding column must be styled ```[name-of-your-geolocation-property]_geolocation```, replacing the bracketed text with the actual name of your geolocation property (e.g. ```detention place_geolocation```).

Step 2: Populate the **CSV file** with your data. Certain properties must follow a specific format:

- If you have opted to use a **Generated ID** property for the **Name** of your entities, leave the rows underneath the “Title” column blank. They will be filled automatically during the import into Uwazi.
- For properties with multiple values, the pipe symbol ```|``` should be used as the separator. Do not include spaces between. For example: 
  - For a **Multiselect** property: ```Arbitrary arrest|Illegal search|Enforced disappearance```
  - For a **Link** property (which follows the format of ```label|URL```): ```Website|https://www.example.com```
  - For a **Geolocation** property (which follows the format of ```latitude|longitude```): ```46.204391|6.143158```
- If you have a **Link** property, the URLs must contain the http or https protocol (e.g. https://www.example.com). Omitting the protocols will cause the import to fail.

Step 3: Save the **CSV file** in UTF-8 format on your computer.

Step 4: Go to the **Library** ![](images/image_0.png) of your Uwazi collection and on the bottom righthand side of the screen, click on the **Import CSV** button. Using the file browser to navigate your computer's storage, find and select the **CSV file**. 

Step 5: Next, select the template that corresponds to the entities you want to upload, using the dropdown menu. 

Step 6: Finally, click the **Import** button. Once the entities are uploaded into your collection, they will appear in the **Library**. You may need to refresh your screen to see them.

Remember, after an import has been done, editing of entities should take place within Uwazi.

### Import entities that contain a Primary Document

If the entities that you would like to import contain a **Primary Document**, you can follow the [previously explained process for importing entities in bulk](#) with a few additional or modified steps:

Step 1 continued: Add a column in your **CSV file** with the name ```File```. 

Step 2 continued: In the ```File``` column, fill in the file name of each entity’s **Primary Document** (e.g. Example Doc1.pdf). 

Step 3 continued: Be sure to name the **CSV file** as ```import.csv```. Then, compress the CSV file and all of the PDFs into a single ZIP file. The CSV file and the PDFs should all live alongside each other in the root directory of the ZIP file (i.e. not nested in a folder).

Step 4 modified: Using the file browser to navigate your computer's storage, find and select the ZIP file.

### Import entities that contain Supporting Files

If the entities that you would like to import contain **Supporting Files**, you can follow the [previously explained process for importing entities in bulk](#) with a few additional or modified steps:

Step 1 continued: Add a column in your **CSV file** with the name ```Attachments```. 

Step 2 continued: In the ```Attachments``` column, fill in the file name of each entity’s corresponding **Supporting File** (e.g. ```Example1.jpg```). If an entity contains multiple **Supported Files**, use the pipe symbol ```|``` as the separator and do not include spaces between (e.g. ```example.doc|sample.jpg```).

Step 3 continued: Be sure to name the **CSV file** as ```import.csv```. Then, compress the CSV file and all of the Supporting Files into a single ZIP file. The CSV file and the Supporting Files should all live alongside each other in the root directory of the ZIP file (i.e. not nested in a folder).

Step 4 modified: Using the file browser to navigate your computer's storage, find and select the ZIP file.

## How to edit properties on multiple entities

It may be that you need to make the same edit(s) across a large number of entities in your Uwazi collection. Doing so one by one would be time-consuming, so for situations such as these, Uwazi makes it possible to edit multiple entities at once.

Step 1: Go to the **Library** ![](images/image_0.png) of your Uwazi collection. If you prefer to use the **Cards View**, select all of the entities that you want to edit using your operating system’s multiselect commands: 

- Windows: Hold down the CTRL key and click on the cards
- Mac: Hold down the Command key and click on the cards

Alternatively, if you prefer to use the **Table View**: 
- Windows: Hold down the CTRL key and click the checkbox next to each table entry
- Mac: Hold down the Command key and click the checkbox next to each table entry

[Learn more about the different ways to view entities](#) in the **Library**.

Step 2: Once you have selected all of the entities you need, click the **Edit** button in the right sidebar. 

Step 3: Edit whichever properties you would like, then click **Save**.

## How to use Copy From

**Copy From** allows you to quickly copy certain properties from one entity to another, all in one go. 

This feature can be particularly useful in case management workflows. For example, consider a collection that receives submissions through a **Submission Form**. Once a submission is made, it appears in the **Library** ![](images/image_0.png) as an entity, and an administrator might want to mark it as reviewed as well as take notes about next steps -- without making modifications to the original raw submission. They could do so by “transferring” all of the information in the submission to a new type of entity that also includes properties where they can keep track of such internal metadata.

It wouldn’t be very efficient to copy each property on the submission entity and paste them one by one into the new entity, so for situations like these and more, the **Copy From** feature comes in handy.

Step 1: Click on the **Library** icon ![](images/image_0.png) in the top navigation menu.

Step 2: On the bottom right side of the screen, click on the **Create entity** button.

Step 3: Using the **Type** dropdown menu, select which entity template you would like to use for the new entity. If you need to create a new template, [refer to the instructions](#) for doing so in the previous chapter.

Step 4: Click on the **Copy from** button in the bottom right corner. 

Step 5: Using the search bar that has appeared, search for any part of the name of the entity that you would like to copy properties from. Entities containing the searched keyword will appear, alongside their corresponding type of template.

Step 6: Select the entity that you are searching for. The system will automatically recognise the overlapping fields in the source and the destination entities. These fields will be highlighted in light blue. Note: The **Name** property cannot be copied using the **Copy From** feature, so you will need to enter the name of the new entity manually.

Step 7: Once you have entered a new name, click the **Copy Highlighted** button. Notice that the overlapping information has been copied into the new entity. 

Step 8: Fill in any other properties that remain and then click **Save**. (You may always come back to add, edit or delete this information later.)

## How to export entities

The **CSV export** feature allows you to export some or all entities in your Uwazi collection. This can be useful if you would like to conduct more advanced analysis using services outside of Uwazi.

Step 1: Decide which entities you want to export. You can use different filters in the **Library**’s sidebar to select a specific subset of entities in the collection for export. Alternatively, if you want to export all of the entities that exist in the entire collection, leave all filters unchecked.

Step 2: Click on the blue **Export CSV** button on the bottom right side of the screen. A **CSV file** in UTF-8 format will automatically be downloaded to your computer for your use.

## How to print entities 

You can print your entities in the **Library** ![](images/image_0.png) by following the steps below:

Step 1: Decide which entities you want to print. You can use different filters in the **Library**’s sidebar to filter out specific entities you want to print. If you want to print every entity in your collection, leave all filters unchecked. Make sure you load every entity in this case, as only the shown entities in the **Library** will be printed. 

Step 2: Use the keyboard shortcut below to print.
- Windows: Hold down the CTRL key and P
- Mac: Hold down the Command key and P

Step 3 optional: If you do not want any headers and footers or background graphics to appear on your printout, in the print dialog box, click **More Settings** and uncheck these before printing.
 
Step 4 optional: You can print your landing page in the same way.
