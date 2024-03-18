# WORKING WITH ENTITIES IN YOUR COLLECTION 

## Understanding view and edit permissions for entities

An Uwazi collection is made up of types of information called **Entities** that live in the **Library** ![](images/image_0.png). An entity has **Properties**, can hold **Primary Documents** and/or **Supporting Files**, and can have **Relationships** to other entities. Some examples of entities might include a court, a case, a specific person, a report or an event. 

In the **Library**, an entity can be viewed as a card, in a table or on a map (as long as it has an associated geolocation), and can also be filtered according to its **Properties**. [Learn more about how to organise and explore your collection](https://uwazi.readthedocs.io/en/latest/admin-docs/organising-your-collection.html).

By default, the visibility of newly created entities is **Restricted**. In practice, this means that only the user who created an entity as well as all users with **Admin** or **Editor** permissions can see and edit it. 

In order to make an entity visible to everyone who has access to your Uwazi collection, you must click the entity’s **Share** button and explicitly share it with the **Public**. (Keep in mind that if your entire Uwazi collection is configured to be private, **Public** in this case strictly refers to everyone who possesses login credentials. [Learn more about configuring the accessibility of your collection](https://uwazi.readthedocs.io/en/latest/admin-docs/managing-settings.html#make-your-collection-private-or-public).)

For users with login credentials to an Uwazi collection, there are two sets of blue filters that help quickly sort through the visibility settings of different entities. The first set refers to the visibility of all of the entities on a global level: 
- **Restricted**, meaning that only a selected subset of users are able to see and/or edit the entity
- **Published**, meaning that everyone with access to the collection is able to see the entity

The second set of filters indicates which particular entities have been explicitly shared with your individual user account or with a specific user group to which you belong: 
- **Shared as Viewer**, meaning your individual user account or a specific user group to which you belong has been given permission to see the entity
- **Shared as Editor**, meaning your individual user account or a specific user group to which you belong has been given permission to edit the entity

## How to add new entities to the Library

Remember, before you can create a new entity, make sure you have already created a corresponding template. [Learn more about how to create templates](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-create-templates). 

To create a new entity:

Step 1: Click on the **Library** icon ![](images/image_0.png) in the top navigation menu. 

Step 2: At the bottom of the screen, click on the **Create Entity** button.

Step 3: Select which template to use from the list, give the entity a name and fill in any of the properties that you want to include. (You may always come back to add, edit or delete this information later.)

Step 4: Click the **Save** button once you have finished.

Step 5: If the entity is intended to feature any PDFs (**Primary Document**), click the **Addd PDF** button and select the desired PDF(s) from within the file browser. 

If the entity is intended to feature any other attached materials (**Supporting Files**), click the **Add File** button and select the desired file(s) from within the file browser. 

Step 6: Decide who should be able to see and edit the entity. By default, the new entity is only visible to you and other users with **Admin** or **Editor** permissions. To change these settings, click on the **Share** button in the right sidebar. 

Add any new users (individuals or groups) who should have access to the entity, choose if they should be able to see and/or edit the entity, and click **Save changes**. Remember, if you’d like the entity to be available to everyone who has access to your Uwazi collection, make sure to share it with the **Public**.

- If you are documenting information about human rights violations using the mobile app Tella, you can also add new entities to your Uwazi collection directly from Tella. [Learn more about the Tella-Uwazi integration](https://uwazi.readthedocs.io/en/latest/admin-docs/integrations-available.html#integrations-available-in-uwazi).

## How to directly add PDFs to the Library

Uwazi particularly supports the management of collections of documents in PDF format. Numerous functions can be carried out when a PDF is uploaded as a **Primary Document** within an entity, such as conducting full text search, creating a clickable table of contents, creating text references, and more. As such, Uwazi makes it possible to quickly upload one or many PDF(s) directly into the **Library**.

Step 1: Click on the **Library** icon ![](images/image_0.png) in the top navigation menu. 

Step 2: At the bottom of the screen, click on the **Upload PDF(s) to Create** button.

Step 3: Select the desired PDF(s) from within the file browser. (To select more than one file, hold down the CTRL key or the Command key before clicking.)

Step 4: Once uploaded, the PDF will appear attached to a new entity in the **Library** with a **Name** property that is automatically filled in with the PDF file's name. 

Step 5: You can edit the name of the entity by automatically pulling out the content in the PDF file. Click on the **View** button in the right sidebar to view your file, and click on the **Edit** button.

Step 5 optional: Within the document, use the cursor to highlight the text that you want to use as the name of the entity. **Click to fill**, written in blue, will appear in the sidebar. Click on **Click to fill**, and the highlighted text will appear as the name. You can also edit other aspects of the entity in the sidebar. Make sure to save any changes you make.

Step 6: Decide who should be able to see and edit the entity. By default, the new entity is only visible to you and other users with **Admin** or **Editor** permissions. To change these settings, click on the **Share** button in the right sidebar.

Add any new users (individuals or groups) who should have access to the entity, choose if they should be able to see and/or edit the entity, and click **Save changes**. Remember, if you’d like the entity to be available to everyone who has access to your Uwazi collection, make sure to share it with the **Public**.

## How to add entities in bulk with CSV import

It may be that you have a large pre-existing collection of data that you wish to migrate to your Uwazi collection. Manually adding them one by one would be a tedious task, so for situations such as these, Uwazi makes it possible to upload them in bulk by using CSV import. For CSV import, prepare your dataset in spreadsheets and then convert it to a **Comma-Separated Values (CSV) file** following the guidelines below. However, please note that CSV import is best suited for the initial migration, and we recommend manually populating your Uwazi collection once the initial migration is complete. Please contact HURIDOCS if you need support on data migration.

### Import entities without documents or supporting files

Remember, before you can import entities in bulk, make sure you have already created a corresponding template. [Learn more about how to create templates](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-create-templates).

Step 1: Create a **spreadsheet**. In your **spreadsheet**, create a column for each property that is included in the template you want to import your dataset into. Provide a header for every column following the guidelines below.

- Name the column header the same as the title of each property in your template. CSV import works by matching the column headers in your **spreadsheet** with the property titles in your template. Therefore, it is important to label each column following the corresponding property’s title in your template. Please note the exceptions below.
  - The first column header should be labeled as **Title** and is required in your **spreadsheet**.
  - If you have a **Geolocation** property, its corresponding column in your **spreadsheet** must be labeled as following: ```[name-of-geolocation-property]_geolocation```. Replace the bracketed text with the actual name of your geolocation property (e.g. ```detention place_geolocation```).
- The column header is not case sensitive but space sensitive. Which means you can use letter cases that are different from your property titles for the column headers, but you have to have the same spacing.

Step 2: Organize your pre-existing data into each corresponding column created in the previous step, following the formats and guidelines below.

- **Date added** and **Date modified** property
  - You should not include these two properties in your **spreadsheet** as they are filled automatically during the import into Uwazi.
- **Select** property
  - If you want to import a **Select** property, you can populate your **spreadsheet** with corresponding thesauri values. [Learn more about Select property and Thesauri](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#select-property). Upon your import, Uwazi will automatically add the imported values to corresponding thesauri if they are not already present.
  - If you want to import a **Select** property that utilises a **Thesaurus** containing terms which are organised into groups, follow the same guidance as the previous step: populate your **spreadsheet** with thesauri values. Do not include the names of the group, instead, simply include the terms that are contained within the groups. Uwazi will automatically assign them to their corresponding groups upon import. [Learn more about how to group your thesaurus](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-create-thesauri).
      -  For example, imagine you have a **Thesaurus** titled ```Country``` in which you grouped ```Bangladesh```, ```Cambodia```, and ```India``` under ```Asia```. In your **spreadsheet** in the rows under the column labeled ```Country```, you would only put ```Bangladesh```, ```Cambodia```, or ```India```. Do not include ```Asia```, as Uwazi will automatically assign the group.
      -  Unlike the case when you import a **Select** property with one-level **Thesaurus**, when importing a **Select** property with grouped (two-level) **Thesaurus**, the corresponding **Thesaurus** must already exist in your collection. Without the predefined grouped **Thesaurus**, the import will not work as Uwazi cannot identify which group each **Thesaurus** values should be assigned to. [Learn more about how to import Thesauri](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-import-thesauri-from-a-csv-file).
  - If you want to import a **Multiple Select** property with multiple thesauri values, use the pipe symbol | as the separator between your values and do not include spaces between each value (e.g.  ```Arbitrary arrest|Illegal search|Enforced disappearance```).
- **Relationship** property
  - If you want to import a **Relationship property**, you have to specify the target template you want to connect your datasets with prior to your import. Navigate to the **Settings** area  and click on **Templates**. Under your **Relationship** property, choose the target template from the **Entity** dropdown.
      -  The target entities related to your dataset you are importing will be automatically created upon the CSV import; you can manually add additional metadata of the related entities within Uwazi. In case of inheriting certain properties from the related entities, you have to populate the target entities with relevant properties in your collection prior to your import.
  - Once the target template is specified, populate the column for the **Relationship** property in your **spreadsheet** with the title of each related target entity. In the case of connecting with multiple entities, use the pipe symbol | as the separator and do not include spaces between each value (e.g. ```Arbitrary arrest|Illegal search|Enforced disappearance```). 
  - If you have a **Relationship** property that inherits a property from the related template, follow the same guidance as the previous step: populate your **spreadsheet** with the title of the target entity, not with the inherited property value. Uwazi will automatically inherit the value from the target entity you specified.
- **Date** property
  - When preparing your **spreadsheet** with a **Date** property, follow the default date format of your Uwazi collection. You have to use the date format consistently throughout your dataset. 
      -  You can check or change your collection’s default date format in **Collection** under **Settings**.
  - In the case you configured a **Multiple Date** property, use the pipe symbol | as the separator and do not include spaces between each date (e.g.```2000/01/01|2000/12/01```).
  - You cannot put invalid dates (e.g. ```2000/02/30```), partial dates (e.g.```2000/01```), or text values (e.g. ```Early 2000```) in your **Date** property.
      -  If your dataset includes partial dates or dates with text values, you can include such information in a **Text** property instead; as **Date** property only recognises valid dates in numeric values.
- **Date Range** property
  - If you wish to import a **Date Range** property, as with the **Date** property, you should follow the default date format of your Uwazi collection.
  - The start and end dates of a date range should be separated with the colon symbol : without spaces (e.g. ```2000/01/01:2000/12/01```).
      -  For a date range without a start or end date, use the colon symbol : as a separator and leave the missing dates blank (e.g. ```2000/01/01:```or ```:2000/12/01```).
  - In the case you configured a **Multiple Date Range** property, use the pipe symbol | as the separator and do not include spaces between each date range (e.g. ```2000/01/01:2000/12/01|2015/01/01:2015/12/01```).
- **Link** property
  - If you have a **Link** property, the URLs must contain the http or https protocol (e.g. ```https://www.example.com```). Omitting the protocols will cause the import to fail.
  - If you want to label your URL, follow the format of ```label|URL``` (e.g. ```HURIDOCS Website|https://huridocs.org```) using the pipe symbol | as the separator without spaces between.
  - If you wish to import multiple links, you can use a **Rich Text*** property instead using the Markup syntax for links (e.g.```[HURIDOCS Website]|https://huridocs.org```). 
- **Geolocation** property
  - If you wish to import a **Geolocation** property, as explained above, it is important to label your column following the format:```[name-of-geolocation-property]_geolocation. Replace the bracketed text with the actual name of your geolocation property``` (e.g. ```detention place_geolocation```). This allows Uwazi to convert your values into geolocation values.
  - Define your latitude and longitude coordinates in decimal degrees (DD) following the format of latitude|longitude (e.g. ```34.0566|-117.1957```) with the pipe symbol | separator without spaces in between. 
      -  When importing **Geolocation** property, Uwazi only recognise numeric values in the decimal degrees (DD) notation format without any marks. For example, coordinate values such as ```N34.0566|W117.1957``` or ```34° 3'| -117° 11'``` should be converted to ```34.0566|-117.1957```.
- **Generated ID** property
  - If you have opted to use a Generated ID as your entities’ default title, leave the Title column in your **spreadsheet** blank. They will be filled automatically during the import process.
 
Step 3: Save the **spreadsheet** and convert it to a **CSV file** in **UTF-8 format** on your computer. 

Step 4: Go to the **Library** of your Uwazi collection and at the bottom of the screen, click on the **Import CSV** button. Using the file browser to navigate your computer’s storage, find and select the **CSV file**.

Step 5: Next, select the template that corresponds to the entities you want to upload, using the dropdown menu. 

Step 6: Finally, click the **Import** button. Once the file is uploaded into your collection, they will appear in the **Library**. You may need to refresh your screen to see them. 

Remember, after an import has been done, editing of entities should take place within Uwazi.


### Import entities that contain a Primary Document

If the entities that you would like to import contain a **Primary Document**, you can follow the [previously explained process for importing entities in bulk](https://uwazi.readthedocs.io/en/latest/admin-docs/working-with-entities-in-your-collection.html?highlight=csv%20in%20bulk#how-to-add-entities-in-bulk-with-csv-import) with a few additional or modified steps:

Step 1 continued: Add a column in your **CSV file** with the name ```File```. 

Step 2 continued: In the ```File``` column, fill in the file name of each entity’s **Primary Document** (e.g. Example Doc1.pdf). 

Step 3 continued: Be sure to name the **CSV file** as ```import.csv```. Then, compress the CSV file and all of the PDFs into a single ZIP file. The CSV file and the PDFs should all live alongside each other in the root directory of the ZIP file (i.e. not nested in a folder).

Step 4 modified: Using the file browser to navigate your computer's storage, find and select the ZIP file.

### Import entities that contain Supporting Files

If the entities that you would like to import contain **Supporting Files**, you can follow the [previously explained process for importing entities in bulk](https://uwazi.readthedocs.io/en/latest/admin-docs/working-with-entities-in-your-collection.html?highlight=csv%20in%20bulk#how-to-add-entities-in-bulk-with-csv-import) with a few additional or modified steps:

Step 1 continued: Add a column in your **CSV file** with the name ```Attachments```. 

Step 2 continued: In the ```Attachments``` column, fill in the file name of each entity’s corresponding **Supporting File** (e.g. ```Example1.jpg```). If an entity contains multiple **Supported Files**, use the pipe symbol ```|``` as the separator and do not include spaces between (e.g. ```example.doc|sample.jpg```).

Step 3 continued: Be sure to name the **CSV file** as ```import.csv```. Then, compress the CSV file and all of the Supporting Files into a single ZIP file. The CSV file and the Supporting Files should all live alongside each other in the root directory of the ZIP file (i.e. not nested in a folder).

Step 4 modified: Using the file browser to navigate your computer's storage, find and select the ZIP file.

### Import entities in multiple languages

It may be that you have a pre-existing collection of data in multiple languages that you wish to migrate to your Uwazi collection. In such a case, you can prepare and import your multilingual collection depending on the characteristics of data and their properties. 

- For **Title**, **Text**, or **Rich Text** properties, you can use CSV import for multilingual collections following the guidelines in the next paragraph.
- For **Select** properties, you can translate them within the Uwazi system without needing to prepare your dataset in multi-languages for CSV import.
- For **Numeric**, **Date**, **Geolocation**, or **Unique ID** properties that are not language specific, there is no additional preparation needed.

If you have unique contents in **Title**, **Text**, or **Rich Text** properties that vary from entity to entity (e.g. ```names```, ```addresses```, or ```descriptions```) and wish to import those in multiple languages to your collection, you can prepare a **spreadsheet** following [the previously explained process for importing entities in bulk](https://uwazi.readthedocs.io/en/latest/admin-docs/working-with-entities-in-your-collection.html#how-to-add-entities-in-bulk-with-csv-import) with a few modified steps: 

Step 1 continued: In addition to the columns created in a default language, create an additional column for every **Title**, **Text**, or **Rich Text** properties in your dataset as per the number of languages you wish to import. 

- For example, if you wish to have your collection in French and Arabic in addition to the default language of English, you will have three columns in your **spreadsheet** for every **Title**, **Text**, or **Rich Text** properties in respective languages.
  
Step 1 continued: Once you create columns for every **Title**, **Text**, or **Rich Text** properties in each language, it is important to label the columns following the format: ```[name-of-corresponding-property]__language-code```. 

- For example, if you have a **Text** property of ```Address``` in English, Arabic, and French, each column should be labeled as ```Address__en```, ```Address__ar```, and ```Address__fr```.
      -  You have to use accurate language codes for each language. Navigate to the **Settings** area  and then click on **Languages** to see language codes for all available languages. 

Step 2 continued: Populate the additional columns in languages you wish to import.

Next, follow the same guidelines of Step 3 through 6 above.

If you have a **Select** property with **Thesauri**, you can translate **Thesauri** within the Uwazi system prior to the import. You can then prepare your **spreadsheet** in one default language without needing to populate the entire dataset in multiple languages, as Uwazi will assign corresponding translations upon your import. There are two ways to translate your **Thesauri** within Uwazi as follows.
- [Learn more about how to import multilingual Thesauri](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-import-thesauri-from-a-csv-file)
- [Learn more about how to translate Thesauri](https://uwazi.readthedocs.io/en/latest/admin-docs/translating-your-collection.html#translate-the-name-label-of-properties-thesauri-relationship-types-custom-filters-and-custom-navigation-menu-items)

If you have **Numeric**, **Date**, **Geolocation**, or **Unique ID**  properties, you can prepare your **spreadsheet** in one default language without needing to populate the entire dataset in multiple languages as values in such properties are not language specific. 


## How to edit properties on multiple entities

It may be that you need to make the same edit(s) across a large number of entities in your Uwazi collection. Doing so one by one would be time-consuming, so for situations such as these, Uwazi makes it possible to edit multiple entities at once.

Step 1: Go to the **Library** ![](images/image_0.png) of your Uwazi collection. If you prefer to use the **Cards View**, select all of the entities that you want to edit using your operating system’s multiselect commands: 

- Windows: Hold down the CTRL key and click on the cards
- Mac: Hold down the Command key and click on the cards

Alternatively, if you prefer to use the **Table View**: 
- Windows: Hold down the CTRL key and click the checkbox next to each table entry
- Mac: Hold down the Command key and click the checkbox next to each table entry

[Learn more about the different ways to view entities](https://uwazi.readthedocs.io/en/latest/admin-docs/organising-your-collection.html#how-to-view-entities-and-documents) in the **Library**.

Step 2: Once you have selected all of the entities you need, click the **Edit** button in the right sidebar. 

Step 3: Edit whichever properties you would like, then click **Save**.

## How to use Copy From

**Copy From** allows you to quickly copy certain properties from one entity to another, all in one go. 

This feature can be particularly useful in case management workflows. For example, consider a collection that receives submissions through a **Submission Form**. Once a submission is made, it appears in the **Library** ![](images/image_0.png) as an entity, and an administrator might want to mark it as reviewed as well as take notes about next steps -- without making modifications to the original raw submission. They could do so by “transferring” all of the information in the submission to a new type of entity that also includes properties where they can keep track of such internal metadata.

It wouldn’t be very efficient to copy each property on the submission entity and paste them one by one into the new entity, so for situations like these and more, the **Copy From** feature comes in handy.

Step 1: Click on the **Library** icon ![](images/image_0.png) in the top navigation menu.

Step 2: At the bottom of the screen, click on the **Create Entity** button.

Step 3: Using the **Type** dropdown menu, select which entity template you would like to use for the new entity. If you need to create a new template, [refer to the instructions](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-create-templates) for doing so in the previous chapter.

Step 4: Click on the **Copy From** button located at the bottom of the screen. 

Step 5: Using the search bar that has appeared, search for any part of the name of the entity that you would like to copy properties from. Entities containing the searched keyword will appear, alongside their corresponding type of template.

Step 6: Select the entity that you are searching for. The system will automatically recognise the overlapping fields in the source and the destination entities. These fields will be highlighted in light blue. Note: The **Name** property cannot be copied using the **Copy From** feature, so you will need to enter the name of the new entity manually.

Step 7: Once you have entered a new name, click the **Copy Highlighted** button. Notice that the overlapping information has been copied into the new entity. 

Step 8: Fill in any other properties that remain and then click **Save**. (You may always come back to add, edit or delete this information later.)

## How to export entities

The **CSV export** feature allows you to export some or all entities in your Uwazi collection. This can be useful if you would like to conduct more advanced analysis using services outside of Uwazi.

Step 1: Decide which entities you want to export. You can use different filters in the **Library**’s sidebar to select a specific subset of entities in the collection for export. Alternatively, if you want to export all of the entities that exist in the entire collection, leave all filters unchecked.

Step 2: Click on the **Export CSV** button at the bottom of the screen. A **CSV file** in UTF-8 format will automatically be downloaded to your computer for your use.

## How to print entities 

You can print your entities in the **Library** ![](images/image_0.png) by following the steps below:

Step 1: Decide which entities you want to print. You can use different filters in the **Library**’s sidebar to filter out specific entities you want to print. If you want to print every entity in your collection, leave all filters unchecked. Make sure you load every entity in this case, as only the shown entities in the **Library** will be printed. 

Step 2: Use the keyboard shortcut below to print.
- Windows: Hold down the CTRL key and P
- Mac: Hold down the Command key and P

Step 3 optional: If you do not want any headers and footers or background graphics to appear on your printout, in the print dialog box, click **More Settings** and uncheck these before printing.
 
Step 4 optional: You can print your landing page in the same way.
