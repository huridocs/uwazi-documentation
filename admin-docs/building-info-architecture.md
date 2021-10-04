# BUILDING YOUR INFORMATION ARCHITECTURE

## How to create templates and add properties

An Uwazi collection is made up of types of information called entities that live in the Library ![](images/image_0.png). But before you can add an entity, you must create a template for it. A template gives an entity a standardised structure. It contains metadata properties of various formats, including: 

- Plain text 
- Numeric 
- Single select dropdown (requires a **Thesaurus**) 
- Multiselect dropdown (requires a **Thesaurus**) 
- Date, date range, multi date, multi date range 
- Rich text 
- Geolocation 
- External link 
- Image and media (to embed image, video or audio) 
- Relationship (to create connections between this type of entity and another type) 
- Preview (to display a thumbnail image of the first page of a **Primary Document**)  
- Generated ID (to assign an automatically generated unique ID code to each entity)

### Add different properties to a template

All templates include two default properties: Title and Date Added. The rest are up to you! You can add as few or as many as you wish. Each property that you add to your template will provide a consistent space to include details about the entity.

Step 1: Navigate to the **Settings** area and click on **Templates**. 

Step 2: Click on the green **Add Template** button.

Step 3: Name your template and select a color for it.

Step 4: On the right side is a list of **Properties**.  Drag and drop one property at a time onto the template or click on the + icon to add the property. 
![](images/image_16.png)

Step 5: For each property, click **Edit** and give it a **Name** or **Label**. Review the other options for the property, which may include the following: 

- **Priority sorting** means that this property will be used as default sorting criterion in the Library.
- **Generated ID** in the title property means that Uwazi will assign an automatically generated unique ID code as the title of the entity. 
- **Select list**: For Select and Multi Select properties, you must choose which **Thesaurus** will be used for this property. 
- **Hide label** means that this property will be displayed without its name or label. 
- **Required property** will prevent the entity from being saved if this property isn’t filled in.
- **Show in cards** means that when the entities in the Library are viewed as cards, this property will be displayed on the card, making it visible without having to click on an entity to see it in its entirety.
  - Note: the cards in the Library will also show a person’s current sorting criterion even if that property is not configured to “Show in cards.” For example, this happens frequently with the “Date added” property, which is the default sorting criterion in the library. When the cards are sorted by “Date added,” the “Date added” property is visible in the cards to demonstrate why the cards are in their current order. 
- **Use as filter** makes it possible to use this property as a  filter in the Library. When someone visits the Library and selects the corresponding type of template among the main filters in the Library’s sidebar, the option to further filter all of the entities by this property will then appear. Learn more about how to configure filters.
- **Default filter** makes it so the property always shows as a filter in the Library’s sidebar by default, no matter if the corresponding type of template among the main filters is selected or not. 
- **Full width** will show this property using the full width available (applies to Media, Image, and Preview properties). 

Step 6: Remember to click on **Save** after creating or making changes to each template.

![](images/image_17.png)

- [Watch a screencast](https://drive.google.com/open?id=1pqcKphveaHFJqrrBPT53b2jE5lo75BMf).
- If you intend to add your entities in bulk using CSV import, remember that the property names on these templates must match the property names in the CSV file. [Learn more about CSV import](https://uwazi.readthedocs.io/en/latest/admin-docs/working-with-entities-in-your-collection.html#how-to-import-in-bulk).

> **Warning:** Uwazi does not support the use of non-Latin characters (such as Arabic text or accented characters) on template configuration. This includes template titles and property names. In order to use non-Latin characters in template titles or property names, you must first create them in Latin characters, and then translate those phrases under the "Translations" tab in Settings as described in [How to translate your content](https://uwazi.readthedocs.io/en/latest/admin-docs/translating-your-collection.html#how-to-translate-your-content). If this is not done, it will trigger a known bug. Our developers are working to fix it.

## How to create Thesauri

In Uwazi, **Thesauri** refers to lists of terms that are referenced in Select and Multiselect properties. Thesauri is the plural form of thesaurus.
 
Using a **Thesaurus** will make your entities more precise and consistent.

Step 1: Navigate to the **Settings** area and click on **Thesauri**. Here you will see all the Thesauri that have been created so far.

Step 2: Click on the green **Add thesaurus** button.

Step 3: Name your **Thesaurus**.

Step 4: Add terms to your Thesaurus by typing them in the spaces provided.

Step 5: Organise your Thesaurus. There are three main ways to organise the terms on your list:
- Moving items around by dragging and dropping
- Clicking the blue Sort button to order the items alphabetically
- Grouping certain terms together. Click on the **Add group** button. Give the group a name. Underneath the name, you can add terms by typing them in the spaces provided. Alternatively, you can drag and drop existing terms into the group.

Step 6: When you are finished, click **Save**. 

![](images/image_18.png)

### Import thesauri from csv files

This feature allows you to import terminology lists to use as an Uwazi thesaurus. The import feature can be used to include lists in new and existing thesauri.

Step 1: Prepare the csv file to import the thesaurus.

- If you have your data saved in a spreadsheet like Microsoft Excel or Google Sheets, be sure to convert the file to csv format before you import it into Uwazi.

- If you only have one language in your instance, then you will only have that one column in your file and the name of the column will be that language.

- However, if you are importing terminology lists in different languages all at once, the csv file should have a separate column for each language that you want to import.

- Please ensure the language is used as the name of the column. Use the name of the language written in English, e.g. "English," “Arabic,” “Spanish.”

- Each row should contain a term and its translations in different languages.

Here's a sample CSV file viewed as plain text:

English,French,German

Man,Homme,Mann

Woman,Femme,Frau

Child,Enfant,Kind

Here's the same file viewed in a spreadsheet program:

![](images/image_19.png)

Step 2: Click the blue **Import** button, and locate and open the csv file.

Step 3: **Save** the thesauri.

**Note:**

- If your csv file has columns for languages that are not enabled in your Uwazi instance in the Languages section, they will be ignored.

- Be careful not to have rows with duplicate values in the same column as this will cause a validation error.

### View the newly imported thesauri

If you imported more than one language into a thesaurus. Then you can follow the next steps to look at your newly added thesaurus.

- Click on **Settings**, click on **Translations**.

- Select the thesaurus that you imported data into. It will display all the languages that have been imported.

## How to connect properties on different templates

Uwazi has a relationship property that can be added as a field on a template. This will allow you to build a connection, or "relationship", with another entity.

Step 1: Go to **Settings** and click on **Relationship types** to add a "type of connection."

- **Note:** You must define your relationship type(s) first in order to connect properties. Doing Step 1 ensures that the relationship type(s)that you just created will appear as a dropdown option in the Relationship\* field on your template (see Step 3).

![](images/image_20.png)

Step 2: Go back to **Settings**, and click on **Templates**. Click **Edit** next to the template you want to change, or click **Add template** to create a new template.

Step 3: Drag the **Relationship** property from the right sidebar onto your template, click **Edit** on the newly added line, and rename the **Label**.

![](images/image_21.png)

Step 4: Now select the relationship type under the **Relationship\*** field. The **\*** indicates that this field is mandatory. This dropdown contains the relationship type(s) that have been defined in Step 1.

Step 5: In the Entities dropdown, you can select which template the template you’re currently editing will be connected to. You can either pick "Any entity or document" or you have the option to make the connection to only one specific template.

- Note: this dropdown does not contain the template that is currently being edited. If you want to connect entities of the same template (for example, connecting two Person entities), click [here](https://uwazi.readthedocs.io/en/latest/admin-docs/organising-your-collection.html#how-to-create-relationships) to see **How to Create Relationships**.

![](images/image_22.png)

Step 6: If you choose a **specific template** in Step 5, another option will automatically appear -- it is a checkbox called **Inherit property**. If you select the **Inherit property** checkbox, a dropdown appears containing the properties of the template selected in Step 5. Once you choose a property from your options, this property will be inherited from the related entities and be visible as metadata for this type of entity.

![](images/image_23.png)

### When to inherit properties from other entities

There are times when it is useful to display a property on more than one entity.

For example, if your data model includes an entity type that captures information about prisoners, and an entity type that captures information about the jail in which they were detained, you may want to be able to display the location of the prisoners on a map via the location of the jails.

Instead of duplicating the geolocation property and collecting the same data twice (once in the **prisoner** entity template, and again in the **jail** template), Uwazi supports the ability to inherit a property from one entity type to another, via a relationship.

The first step is to create the property for which you want to be inherited. To use the example above, you will create the geolocation property on the **jail** entity template. This will serve as the one place to capture the geolocation of the jails.

The next step is to [create a relationship type](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-connect-properties-on-different-templates) that will represent the relationship between the **jail** and the **prisoner**. You may want to call this something like "location" or "jail". For this example, we'll use the name "jail".

The next step is to create a relationship property _from_ the entity template that you want to inherit a property, _to_ the entity type that has the property you want to inherit. To use the example above, you will edit the **prisoner** entity template to add a relationship property. The name of this relationship property is whatever you named the relationship in the previous step ("jail"). As you are creating this relationship property, you will be asked to select which entity type you want the relationship to include and you will select "Jail" because that is the entity type that has the geolocation property you want to inherit. Then you will be asked if you want to inherit a property from the "Jail" entity template. Here is where you can select the geolocation property.

![](images/image_24.png)

Now that these two entity types have this relationship established and the inherited property, when you create a relationship between prisoner X and jail Y, the prisoner X entity will inherit the geolocation of jail Y, allowing you to show the location of the prisoner (or prisoners) on a map.

![](images/image_25.png)

This is the equivalent to a foreign key in a relation database that gets resolved to a particular property of the linked record.
