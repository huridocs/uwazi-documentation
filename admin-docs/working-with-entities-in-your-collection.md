# WORKING WITH ENTITIES IN YOUR COLLECTION 

## Understanding entities

An Uwazi collection is made up of entities, which contain properties, can feature documents or supporting files, and can have connections to one another. Some examples of entities might include a court, a case, a specific person or an event. 

All of the entities in an Uwazi collection live in an area called the Library ![](images/image_0.png), where they can be viewed as cards, in a table or on a map (as long as entities have an associated geolocation), and can also be filtered according to their properties.

By default, the visibility of newly created entities is restricted. In practice, this means that only the user who created an entity as well as all users with admin or editor permissions can see and edit it. In order to make an entity visible to everyone who has access to your Uwazi collection, it must be shared accordingly with the “Public”. 

(Keep in mind that if your entire Uwazi collection is configured to be private, “Public” in this case strictly refers to everyone who possesses log-in credentials.)

For users with log-in credentials to an Uwazi collection, there are two sets of blue filters that help quickly sort through the visibility settings of different entities. The first set refers to the visibility of all of the entities on a global level: 
- “Restricted”, meaning that only a selected subset of users are able to see and/or edit the entity
- “Published”, meaning that everyone with access to the collection is able to see the entity

The second set indicates which particular entities have been explicitly shared with your individual user account or with a specific user group to which you belong: 
- “Can view”, meaning your individual user account or a specific user group to which you belong has been given permission to see the entity
- “Can edit”, meaning your individual user account or a specific user group to which you belong has been given permission to edit the entity

## How to add new entities to the Library

Remember, before you can create a new entity, make sure you have already created a corresponding template.

To create a new entity:

Step 1: Click on the Library icon ![](images/image_0.png) in the top navigation menu. 

Step 2: On the bottom right hand side of the screen, click on the **Create entity** button.

Step 3: Select which template to use, give the entity a title and fill in any of the properties that you want to include. (You may always come back to add, edit or delete this information later.)

Step 4: Click the **Save** button once you are finished.

Step 5: If the entity is intended to feature a PDF (“[Primary Document](https://uwazi.readthedocs.io/en/latest/admin-docs/glossary-of-terms.html#)”), click the **Upload PDF** button in the entity pane and select the desired PDF from within the file browser. 

If the entity is intended to feature any other attached materials (“[Supporting Files](https://uwazi.readthedocs.io/en/latest/admin-docs/glossary-of-terms.html#)”), click the **Add supporting file** button and select the desired file(s) from within the file browser. 

Step 6: Decide who should be able to see and edit the entity. By default, the new entity is only visible to you and other users with admin or editor permissions. 

To change these settings, click on the Share button in the entity pane. Add any new users (individuals or groups) who should have access to the entity, choose if they should be able to see and/or edit the entity, and click **Save changes**. 

Remember, if you’d like the entity to be available to everyone who has access to your Uwazi collection, make sure to share it with the “Public”.

## How to directly add PDFs to the Library

Uwazi particularly supports the management of collections of documents in PDF format. Numerous functions can be carried out when a PDF is uploaded as the "[Primary Document](https://uwazi.readthedocs.io/en/latest/admin-docs/glossary-of-terms.html#)" within an entity, such as conducting full text search, creating a clickable table of contents, creating text references, and more.

If many of the entities in your collection feature a "primary" PDF document, it could become tedious to create entity after entity, giving them a title and filling in any properties, and only after they are saved, finally adding a PDF.

For situations such as these, Uwazi makes it possible to upload PDF(s) directly into the Library as a first step without the prior creation of an entity.

To directly add PDF(s) to the Library:

Step 1: Click on the Library icon ![](images/image_0.png) in the top navigation menu. 

Step 2: On the bottom righthand side of the screen, click on the **Upload PDF(s) to create** button.

Step 3: Select the desired PDF(s) from within the file browser. (To select more than one file, hold down the CTRL key or the Command key before clicking.)

Step 4: Once uploaded, the PDF will appear attached to a new entity in the Library with a title property that is automatically filled in with the PDF file name. To edit the title and other aspects of the entity, click on the **Edit** button in the entity pane. Make sure to save any changes you make.  

Step 5: Decide who should be able to see and edit the entity. By default, the new entity is only visible to you and other users with admin or editor permissions. 

To change these settings, click on the **Share** button in the entity pane. Add any new users (individuals or groups) who should have access to the entity, choose if they should be able to see and/or edit the entity, and click **Save changes**. 

Remember, if you’d like the entity to be available to everyone who has access to your Uwazi collection, make sure to share it with the “Public”.

### How to import in bulk

It may be that you have a large pre-existing collection of data points or materials that you want to add to your Uwazi collection. Doing so one by one would be a tedious task, so for situations such as these, Uwazi makes it possible to upload in bulk by preparing and then importing a **Comma-Separated Values** (CSV) file.

#### Importing entities without documents or files

Remember, before you can import entities in bulk, make sure you have already created a corresponding template.

Step 1: Create a CSV file on your computer. It should include a column for each of the properties that are included on the entity’s template. Import works by matching property names – therefore, be meticulous in using the same column header names in the CSV file as the property names on the template in Uwazi.

- Property names are not case sensitive, which means you can use either lowercase, capitals or a combination of both.
- The “Title” column is required in your CSV file. It serves to identify the entity, but does not have to be unique.
- There is no need to include the “Date Added” property because it is filled automatically during the import into Uwazi.
- If you have a geolocation property, its corresponding column must be styled “[name-of-your-geolocation-property]_geolocation”, replacing the bracketed text with the actual name of your geolocation property (e.g. detention place_geolocation).

Step 2: Populate the CSV file with your data. Certain properties must follow a specific format:

- For properties with multiple values, the pipe symbol | should be used as the separator. Do not include spaces between. For example: 
  - For a multi-select property: Arbitrary arrest|Illegal search|Enforced disappearance
  - For a hyperlink property (which follows the format of label|URL): Website|https://www.example.com
  - For a geolocation property (which follows the format of latitude|longitude): 46.204391|6.143158
- If you have a link property, the URLs must contain the http or https protocol (e.g. https://www.example.com). Omitting the protocols will cause the import to fail.

Step 3: Save the CSV file in UTF-8 format on your computer.

Step 4: Go to the Library of your Uwazi collection and on the bottom righthand side of the screen, click on the **Import CSV** button. Using the file browser to navigate your computer's storage, find and select the CSV file. 

Step 5: Next, select the template that corresponds to the entities you want to upload, using the drop-down menu. 

Step 6: Finally, click the **Import** button. Once the entities are uploaded into your collection, they will appear in the Library. You may need to refresh your screen to see them.

Remember, after an import has been done, editing of entities should take place within Uwazi.

#### Importing entities that contain a Primary Document

If the entities that you would like to import contain a Primary Document, you can follow the previously explained process for importing entities in bulk with a few additional or modified steps:

Step 1 continued: Add a column in your CSV file with the name “File”. 

Step 2 continued: In the “File” column, fill in the file name of each entity’s Primary Document (e.g. ExampleDoc1.pdf). 

Step 3 continued: Be sure to name the CSV file as import.csv. Then, compress the CSV file and all of the PDFs into a single ZIP file. The CSV file and the PDFs should all live alongside each other in the root directory of the ZIP file (i.e. not nested in a folder).

Step 4 modified: Using the file browser to navigate your computer's storage, find and select the ZIP file.

#### Importing entities that contain Supporting Files

If the entities that you would like to import contain Supporting Files, you can follow the previously explained process for importing entities in bulk with a few additional or modified steps:

Step 1 continued: Add a column in your CSV file with the name “Attachments”. 

Step 2 continued: In the “Attachments” column, fill in the file name of each entity’s corresponding Supporting File (e.g. Example1.jpg).
 If an entity contains multiple Supported Files, use the pipe symbol | as the separator and do not include spaces between (e.g. example.doc|sample.jpg)

Step 3 continued: Be sure to name the CSV file as import.csv. Then, compress the CSV file and all of the Supporting Files into a single ZIP file. The CSV file and the Supporting Files should all live alongside each other in the root directory of the ZIP file (i.e. not nested in a folder).

Step 4 modified: Using the file browser to navigate your computer's storage, find and select the ZIP file.

### How to edit properties on multiple entities

It may be that you need to make the same edit(s) across a large number of entities in your Uwazi collection. Doing so one by one would be time-consuming, so for situations such as these, Uwazi makes it possible to edit multiple entities at once.

Step 1: Go to the Library of your Uwazi collection. If you prefer to use the Library’s Cards View, select all of the entities that you want to edit using your operating system’s multi-select commands: 

- Windows: Hold down the CTRL key and click on the cards
- Mac: Hold down the Command key and click on the cards

Alternatively, if you prefer to use the Library’s Table View: 
- Windows: Hold down the CTRL key and click the checkbox next to each table entry
- Mac: Hold down the Command key and click the checkbox next to each table entry

Step 2: Once you have selected all of the entities you need, click the **Edit** button in the entity pane. 

Step 3: Edit whichever properties you would like, then click **Save**.

### How to configure main and secondary filters

Filters appear on the righthand sidebar of the Library. They help users quickly navigate an Uwazi collection as well as generate basic conclusions about its contents.

#### Configure main filters

The main filters are derived from the types of entity templates that exist in your collection. You can define which ones can be used as filters in the Library’s sidebar, customize the order in which the filters appear, and group certain ones together under a label of your choosing.  

Step 1: Click on the Settings icon in the top navigation menu and then click on Filters.

Step 2: On the righthand side in an area named “Entity types”, you will see a list of your templates. For each template that you want to be able to filter in the Library, drag and drop the corresponding item into the space labeled “Drag items here” in the order in which you would like it to appear.

Step 3: If you would like to group certain filters together, click on the **Create group** button. Give the group a descriptive label. Underneath the label, drag and drop the items that you would like to appear in the group. 

Step 4: Once finished, **Save** the changes you have made.

#### Configure a second tier of filters on the sidebar

Besides using the types of templates as filters, you can also select which specific properties on the entities act as filters.

Step 1: Click on the Settings icon in the top navigation menu and then click on Templates.

Step 2: Select the **Edit** button on the type of template you would like to edit.   

Step 3: Find the property that you want to include as a filter in the Library and click on the **Edit** button.

Step 4: Select whichever filter options match your needs: 
- “Use as filter” checkbox: This activates the ability to filter entities according to this property. When a user visits the Library and selects the corresponding type of template among the main filters in the Library’s sidebar, the option to further filter all of the entities by this property will then appear.     
- “Default filter” checkbox: This additional option makes it so the property always shows as a filter in the Library’s sidebar by default, no matter if the corresponding type of template among the main filters is selected or not. 
- “Show in cards” checkbox: While not technically a filter, this additional option makes it so the property appears in the entity card within the Library’s Cards View. Selecting this option on a few key properties can make it easier for users to quickly skim through your collection by sight and identify specific entities.    

Step 5: Click on **Save**. You can now go to the Library and view the filters you have configured. For multi-select properties that you have activated as filters, you will see an “And/Or” toggle next to the filter: 
- Using the AND operator will display the entities that contain all the properties for which you are filtering.
- Using the OR operator will display the entities that contain at least one of the properties for which you are filtering.

### How to use Copy From

Copy From allows you to quickly copy certain properties from one entity to another, all in one go. 

This feature can be particularly useful in case management workflows. For example, consider a collection that receives submissions through a Public Intake Form. Once a submission is made, it appears in the Library as an entity, and an administrator might want to mark it as reviewed as well as take notes about next steps -- without making modifications to the original raw submission. They could do so by “transferring” all of the information in the submission to a new type of entity that also includes properties where they can keep track of such internal metadata.

It wouldn’t be very efficient to copy each property on the submission entity and paste them one by one into the new entity, so for situations like these and more, the Copy From feature comes in handy.

Step 1: Click on the Library icon in the top navigation menu.

Step 2: On the bottom righthand side of the screen, click on the **Create entity** button.

Step 3: Using the “Type” drop-down menu, select which entity template you would like to use.

Step 4: Click on the **Copy from** button in the bottom righthand corner. 

Step 5: Using the search bar that has appeared, search for any part of the title of the entity that you would like to copy properties from. As you search, entities containing the searched keyword will appear, alongside their corresponding type of template. In the image below, the word “Federal” was typed into the search bar.

Step 6: Select the entity that you are searching for. The system will automatically recognise the overlapping fields in the source and the destination entities. These fields will be highlighted in light blue. **Note**: The title property cannot be copied using the Copy From feature, so you will need to enter the title of the new entity manually.

Step 7: Once you have entered a new title, click the **Copy Highlighted** button. Notice that the overlapping information has been copied into the new entity. 

Step 8: Fill in any other properties that remain and then click **Save**. (You may always come back to add, edit or delete this information later.)

### How to export entities

The CSV export feature allows users to export some or all entities in your Uwazi collection for further analysis and visualisation.

Step 1: Decide which entities you want to export. You can use different filters in the Library’s sidebar to select a specific subset of entities in the collection for export. Alternatively, if you want to export all of the entities that exist in the entire collection, leave all filters unchecked.

Step 2: Click on the blue **Export CSV** button on the bottom righthand side of the screen. A CSV file in UTF-8 format will automatically be downloaded to your computer for your use.
