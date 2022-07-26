# BUILDING YOUR INFORMATION ARCHITECTURE

## How to create templates

An Uwazi collection is made up of types of information called **Entities** that live in the **Library** ![](images/image_0.png). An entity has **Properties**, can hold **Primary Documents** and/or **Supporting Files**, and can have **Relationships** to other entities. Before you can create an entity in the **Library**, you must create a **Template** for it, which gives an entity a standardised structure.

To create a template:

Step 1: Navigate to the **Settings** area and click on **Templates**.

Step 2: Click on the green **Add Template** button.

Step 3: Name your template and select a color for it. The combination of the name and color will be used to label entities that utilise this template in the **Library** ![](images/image_0.png).

Step 4: On the right side of the screen is a list of **Properties**. Drag and drop one property at a time onto the template, or click on the plus icon to add the property.

![](images/image_16.png)

Step 5: For each property, click **Edit** and give it a **Name** or **Label**. Configure any necessary settings required for the particular property in question. Be sure to review the other options available for the property, which may include the following:

- **Priority Sorting** means that this property will be used as default sorting criterion in the **Library**.
- **Generated ID** in the **Name** property means that Uwazi will assign an automatically generated unique ID code as the name of the entity.
- **Select List**: For **Select** and **Multiselect** properties, you must choose which **Thesaurus** will be used for this property.
- **Hide Label** means that this property will be displayed without its **Name** or **Label**.
- **Required Property** will prevent the entity from being saved if this property isn’t filled in.
- **Show in Cards** means that when the entities in the **Library** are viewed as cards, this property will be displayed on the card, making it visible without having to click on an entity to see it in its entirety.
  - Note: The cards in the **Library** will also show a person’s current sorting criterion even if that property is not configured to **Show in Cards**. For example, this happens frequently with the **Date Added** property, which is the default sorting criterion in the **Library**. When the cards are sorted by “date added”, the **Date Added** property is visible in the cards to demonstrate why the cards are in their current order.
- **Use as Filter** makes it possible to use this property as a filter in the **Library**. When someone visits the **Library** and selects the corresponding type of template among the **Primary Filters** in the **Library**’s sidebar, the option to further filter all of the entities by this property will then appear. [Learn more about how to configure filters](https://uwazi.readthedocs.io/en/latest/admin-docs/organising-your-collection.html?highlight=filters#how-to-configure-main-and-secondary-filters).
- **Default Filter** makes it so the property always shows as a filter in the **Library**’s sidebar by default, no matter if the corresponding type of template among the **Primary Filters** is selected or not.
- **Full Width** will show this property using the full width available (applies to **Media**, **Image**, and **Preview** properties).

Step 6: Remember to click on **Save** after creating or making changes to each template.

- [Watch a screencast](https://drive.google.com/open?id=1pqcKphveaHFJqrrBPT53b2jE5lo75BMf).
- If you intend to add your entities in bulk using CSV import, remember that the property names on these templates must match the property names in the CSV file. [Learn more about CSV import](https://uwazi.readthedocs.io/en/latest/admin-docs/working-with-entities-in-your-collection.html#how-to-add-entities-in-bulk-with-csv-import).

## Understanding properties

**Properties** are descriptive attributes that are assigned to entities. All entity templates include three default properties: **Name**, **Date Added** and **Date Modified**. The rest are up to you! You can add as few or as many as you wish. Each property that you add to your template will provide a consistent space to include details about the entity.

There are several types of properties available, including:

- Plain text
- Numeric
- Single select (requires a **Thesaurus**)
- Multiselect (requires a **Thesaurus**)
- Relationship (to create connections between this type of entity and another type)
- Date, date range, multi date, multi date range
- Rich text
- External link
- Image (to attach an image)
- Preview (to display a thumbnail image of the first page of a **Primary Document**)
- Media (to embed image, video or audio)
- Geolocation (to add latitude and longitude coordinates that can be displayed on a map)
- Generated ID (to assign an automatically generated unique ID code to each entity)

Some properties are a bit more complex and/or require extra steps to configure them correctly. These include **Select** and **Multiselect**, **Geolocation**, **Relationships** and **Generated ID**.

## Select and Multiselect properties

A **Select** property allows you to assign a single attribute to your entity from a dropdown list of predefined terms. A **Multiselect** property allows you to assign several attributes to your entity from a checklist of predefined terms. Before you can add either a **Select** or **Multiselect** property to a template, you must create your list of predefined terms. In Uwazi, this list is called a **Thesaurus**.

### How to create thesauri

Step 1: Navigate to the **Settings** area and click on **Thesauri**. Here you will see all the **Thesauri** that have been created so far.

![](images/image_18.png)

Step 2: Click on the green **Add Thesaurus** button.

Step 3: Name your **Thesaurus**.

Step 4: Add terms to your **Thesaurus** by typing them in the spaces provided.

Step 5: Organise your **Thesaurus**. There are three main ways to organise the terms on your list:

- Moving items around by dragging and dropping
- Clicking the blue **Sort** button to order the items alphabetically
- Grouping certain terms together. Click on the **Add Group** button. Give the group a name. Underneath the name, you can add terms by typing them in the spaces provided. Alternatively, you can drag and drop existing terms into the group.

Step 6: When you have finished, click **Save**.

### How to import thesauri from a csv file

It may be that you have a list of terms already prepared that you would like to include in a **Thesaurus**. Typing the terms one by one could become tedious, so for situations such as these, Uwazi makes it possible to upload in bulk by preparing and then importing a comma-separated values (CSV) file. This import feature can be used to add terms to new or existing **Thesauri**.

Step 1: Create a **CSV file** on your computer:

- If you only have one language configured in your instance, then you should only have one column in your file. The column label should be the name of the language written in English (e.g. English, Russian, Spanish).
- If you have more than one language configured in your instance and you want to import a list of terms at the same time as their corresponding translations, then each language should have its own separate column. Use the name of the language written in English (e.g. English, Russian, Spanish).
  - Note: If your CSV file has columns for languages that are not configured in your Uwazi instance, they will be ignored. Learn more about enabling different languages in Uwazi.

Step 2: Populate the **CSV file** with the terms. Each term should occupy its own row. For example, here’s a sample CSV file viewed as plain text:

```
English,French,German
Man,Homme,Mann
Woman,Femme,Frau
Child,Enfant,Kind
```

And here’s the same file viewed in a spreadsheet program:
![](images/image_19.png)

- Note: Avoid including duplicate values in the same column, as this will cause a validation error and prevent the import from working successfully.

You can group terms under a parent term by providing the child terms following the parent prefixed with a hyphen.

```
English,French,German
Primary,Primaire,Primär
-Red,-Rouge,-Rot
-Green,-Vert,-Grün
-Blue,-Bleu,-Blau
No color,Sans couleur,Farblos
```

- Note: the prefixing needs to be consistent across translations of a term and all grouped terms need to have a parent. Otherwise, the import will cause a validation error.

Step 3: Save the **CSV file** in UTF-8 format on your computer.

Step 4: Navigate to the **Settings** area and click on **Thesauri**. Click on the green **Add Thesaurus** button and give the **Thesaurus** a name. Alternatively, if you would like to add to an existing **Thesaurus**, click the **Edit** button next to it.

Step 5: Click the blue **Import** button. Using the file browser to navigate your computer’s storage, find and select the CSV file. Once the import has finished, the terms will appear in the **Thesaurus**.

Step 6: Click the green **Save** button.

- If you imported more than one language, navigate to the **Settings** area and click on **Translations**. Click on the **Thesaurus** name, and you will see all the terms and their translations that have been imported. [Learn more about translating an Uwazi collection](https://uwazi.readthedocs.io/en/latest/admin-docs/translating-your-collection.html).
- It is not currently possible to import Thesauri that are already organised into groups. You will need to first import a Thesaurus as described above, and then while working within Uwazi you can organise the terms into whichever groupings you want.

### How to configure a Select or Multiselect property

Step 1: Once you have created your **Thesaurus**, navigate to the **Settings** area and click on **Templates**. Locate the template to which you want to add a **Select** or **Multiselect** property and click **Edit**.

Step 2: Drag and drop the **Select** or **Multiselect** property from the right side of the screen into the template, or add it by clicking on the plus icon next to the property.

Step 3: Click **Edit** and give the property a **Name** or **Label**. Using the **Select List** dropdown, choose the **Thesaurus** that you want to reference in this property.

Step 4: Review the other options for the property as explained previously in this chapter. When you have finished, click **Save**.

## Geolocation property

The **Geolocation** property allows you to add latitude and longitude coordinates to an entity, which can then be displayed as a point on a map. An entity template can have multiple **Geolocation** properties. Depending on the order in which they appear on the template, these geolocation points can be displayed separately on their own individual maps or together in one combined map within the entity.

### How to display multiple geolocation properties on separate maps within the same template

Step 1: Navigate to the **Settings** area and click on **Templates**. Locate the template to which you want to add Geolocation properties and click **Edit**.

Step 2: Drag and drop the **Geolocation** property from the right side of the screen into the template, or add it by clicking on the plus icon next to the property.

Step 3: Click **Edit** and give the property a **Name** or **Label**. Review the other options for the property as explained previously in this chapter.

Step 4: Repeat the above process until you have created all of the **Geolocation** properties that you want.

Step 5: Using the drag and drop function, move the **Geolocation** properties around so that they are not adjacent to each other on the template. In other words, they should be separated by one or more other non-Geolocation properties.

This ensures that each **Geolocation** property will display on its own separate map, each labeled with the **Name** or **Label** that you have given it.

Step 6. When you have finished, click **Save**.

### How to display multiple geolocation properties on one combined map within the same template

Step 1: Navigate to the **Settings** area and click on **Templates**. Locate the template to which you want to add Geolocation properties and click **Edit**.

Step 2: Drag and drop the **Geolocation** property from the right side of the screen into the template, or add it by clicking on the plus icon next to the property.

Step 3: Click **Edit** and give the property a **Name** or **Label**. Review the other options for the property as explained previously in this chapter.

Step 4: Repeat the above process until you have created all of the **Geolocation** properties that you want.

Step 5: Using the drag and drop function, move the **Geolocation** properties around so that they are all adjacent to each other on the template. In other words, they should not be separated by any other non-Geolocation properties placed between them.

When **Geolocation** properties are ordered one after the other, they will display on one map labeled **Combined Geolocations**.

Step 6. When you have finished, click **Save**.

## Relationship property

A **Relationship** property allows you to create a connection to another entity template. The connection can be basic, such that it points in general to a different template. The connection can also be more complex, such that it inherits a specific property from another template.

Before you can add a **Relationship** property, you must first create the **Relationship Type** that will be used to define the nature of the connection.

### How to create relationship types

Step 1: Navigate to the **Settings** area and click on **Relationship Types**.

![](images/image_20.png)

Step 2: Click on the **Add Connection** button. Give the **Relationship Type** a descriptive name.

Step 3: Click **Save**.

### How to configure a basic relationship property

Step 1: Once you have created the **Relationship Type**, navigate to the **Settings** area and click on **Templates**. Locate the template to which you want to add a **Relationship** property and click **Edit**.

Step 2: Drag and drop the **Relationship** property from the right side of the screen into the template, or add it by clicking on the plus icon next to the property.

Step 3: Click **Edit** on the newly added property, and give it a descriptive **Name** or **Label**.

Step 4: Using the dropdown list called Relationship*, select the **Relationship Type** that you would like to use as part of this property. (The * indicates that it is mandatory.)

Step 5: By default, the property will allow you to create a connection to any entity template (“Any entity or document”). However, you also have the option to restrict a connection to only entities that use one specific template. To do so, click on the **Entities** dropdown list and select whichever template you want.

- Note: The dropdown won’t contain the template that is currently being edited. [Learn more about how to connect entities of the same template](#).

Step 6: Review the other options for the property as explained previously in this chapter. When you have finished, click **Save**.

Now, whenever you create a new entity using the template that includes this **Relationship** property, you will be presented with a multiselect list of all the existing entities in your collection which meet the criteria that you have configured (i.e. a connection to another specific template or a connection to “Any entity or document”). Simply select the relevant existing entity (or entities) from the list, and then its **Name** property will be displayed as part of the new entity’s metadata.

- Note: You can also establish a basic connection on an ad hoc basis between entities by creating a Relationship directly in the Information Hub of an entity (without utilising the Relationship property). Learn more.

### How to configure a relationship property that inherits a property from another template

If you would like to configure a **Relationship** property that inherits a property from another template, you can follow [the previously explained process for configuring a basic Relationship property](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-configure-a-basic-relationship-property) with a few modified or additional steps:

Step 5 modified: By default, the property will allow you to create a connection to any entity template (“Any entity or document”). However, in order to activate the more advanced option of inheriting properties from another template, you must specify the template from which you want to inherit. To do so, click on the **Entities** dropdown list and select the relevant template.

Step 6 modified: If you choose a specific template in the previous step, another option will automatically appear: a checkbox called **Inherit Property**. Tick the box and a dropdown will appear containing all of the properties contained within the other template that you have selected. Choose a property from the list to inherit. Be sure to also review the other options for the property as explained previously in this chapter.

Step 7: Review the other options for the property as explained previously in this chapter. When you have finished, click **Save**.

Now, whenever you create a new entity using the template that includes this **Relationship** property, you will be presented with a multiselect list of all the existing entities in your collection which meet the criteria that you have configured (i.e. a connection to another specific template that inherits one of that template’s specific properties).

Simply select the relevant existing entity (or entities) from the list, and then the property that you have chosen to inherit will be displayed as part of the new entity’s metadata.

### How to configure a relationship property that inherits multiple properties from another template

If you would like to configure a **Relationship** property that inherits multiple properties from another template, you can follow the [previously explained process for configuring a basic Relationship property](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-configure-a-basic-relationship-property) with a few modified or additional steps:

Step 5 modified: By default, the property will allow you to create a connection to any entity template (“Any entity or document”). However, in order to activate the more advanced option of inheriting properties from another template, you must specify the template from which you want to inherit. To do so, click on the **Entities** dropdown list and select the relevant template.

Step 6 modified: If you choose a specific template in the previous step, another option will automatically appear: a checkbox called **Inherit Property**. Tick the box and a dropdown will appear containing all of the properties contained within the other template that you have selected. Choose a property from the list to inherit. Be sure to also review the other options for the property as explained previously in this chapter.

Step 7: Repeat the above process as many times as needed: add another **Relationship** property to the template, ensuring that it is configured with the same template from the **Entities** dropdown list and the same **Relationship Type** as previously selected.

Step 8: When you have finished, click **Save**.

Now, whenever you create a new entity using this template, within each of these **Relationship** properties you will be presented with a multiselect list of all the existing entities in your collection which meet the criteria that you have established (i.e. a connection to another specific template that inherits one of that template’s specific properties).

Select the relevant existing entity (or entities) from the list contained within whichever **Relationship** property happens to appear first. Once you do, the same entity (or entities) will also be automatically selected on the other **Relationship** properties.

- Note: When you inherit multiple properties in this way, any changes made to one of the **Relationship** properties of an entity that utilises this template will affect the other **Relationship** properties on this template that share the same connection. For example, If you untick a particular entity within one **Relationship** property, it will also automatically be unticked in the other **Relationship** properties. This is because you have ultimately created one connection with multiple inheritance of properties, instead of multiple separate connections.

Once you save the new entity, the properties that you have chosen to inherit will then be displayed as part of the new entity’s metadata.

### When to inherit properties from other entities

Depending on how you have chosen to structure your collection (in other words, your data model), it can be useful for one entity to inherit a property from another entity because it prevents you from having to enter the same information over and over again.

Here’s a simple example: Imagine that there is a type of entity template in your collection called Country. This entity includes all sorts of details about individual countries, including their geolocation on a map.

Now, imagine that you want to create another type of entity template called Person. You want this template to include all sorts of details about individual people, including the geolocation of their country of birth on a map.

The geolocation of countries is information that already exists in your collection – as a property on the Country entity template – so you can opt to “inherit” it by setting up a connection between the Person template and the Country template. You would do so by following the steps outlined in the previous section:

- Define the **Relationship Type** (e.g. “Country geolocation”)
- Add a **Relationship** property to the Person template
- Select the previously defined **Relationship Type** from the dropdown list
- Select the Country template from the **Entities** dropdown list
- Select the **Inherit Property** checkbox
- Choose the **Geolocation** property to inherit

From this point on, whenever you create a new Person entity in the future, you will be able to select which specific Country entity – from among all of the Country entities in your collection – is connected to the person. Simply select the relevant country and click Save. By doing so, the new Person entity will include the same Geolocation information that is already found on the selected Country entity.

## Generated ID property

Adding a **Generated ID** property to a template means that any time an entity is created using that template, Uwazi will assign it an automatically generated unique ID code. Depending on the configuration you choose, the **Generated ID** can be just another property on the template or it can take the place of the template’s default text-based **Name** property.

### How to add a generated id property to a template

[Follow the steps for creating an entity template and adding properties](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-create-templates) as explained previously in this chapter. **Generated ID** will appear among the property options listed on the right side of the screen. When finished, click **Save**.

### How to use a generated id as the name/title of an entity

[Follow the steps for creating an entity template](https://uwazi.readthedocs.io/en/latest/admin-docs/building-info-architecture.html#how-to-create-templates) as explained previously. In the **Name** property, select the checkbox **Generated ID** to activate the option. When finished, click **Save**.

- You do not have to add a separate **Generated ID** property for this feature to work. If you do add a separate **Generated ID** property, each entity that you create using this template will consequently have two different unique ID codes assigned to it.
