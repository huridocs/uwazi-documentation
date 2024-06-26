# Organising and Exploring Your Collection

## How to view entities and documents

### View entities as cards, in a table or on a map

All of the entities in an Uwazi collection live in an area called the **Library** ![Library icon](images/image_0.png), where they can be viewed as cards, in a table or on a map (as long as entities have an associated geolocation). [Learn more about how to customise the default Library view](managing-settings.md#customise-the-default-library-view).

When exploring your collection, you can freely switch between the different views by toggling the icons found along the top of the **Library** area:

- Click the cards icon ![Cards icon](images/image_0.png) to turn on **Cards view**. When the **Cards view** is activated, simply click on an entity card to expand the right sidebar and see more details about the entity. You can also click the **View** button on the card itself or from within the right sidebar to open the entity in full.
- Click the table icon ![Table icon](images/fa-align-justify.png) to turn on **Table view**. You can customise which columns are shown by using the dropdown menu found along the top of the Library area. When **Table view** is activated, simply select the checkbox next to the entity to expand the right sidebar and see more details. You can also click the **View** button from within the right sidebar to open the entity in full.
- Click on the map icon ![Map marker icon](images/fa-map-marker.png) to turn on **Map view**. This icon will only appear if the entities in your collection have an associated geolocation. Using the layers icons found at the bottom right part of the map, you can toggle between viewing the map in **Streets**, **Satellite** or **Hybrid** view. When **Map view** is activated, simply click on a point within the map to expand the right sidebar and see more details about the entity. You can also click the **View** button from within the right sidebar to open the entity in full.

### Read PDFs within Uwazi

If an entity has a PDF attached as a **Primary Document**, you can view and explore it directly within Uwazi without having to download anything.

Step 1: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity that contains the **Primary Document** you want to read.

Step 2: Either on the entity card or within the right sidebar, click the **View** button. The PDF will be displayed in full.

:::{note}
An entity can feature multiple **Primary Documents**. However, only the first **Primary Document** to be uploaded to an entity will automatically be displayed in full when the entity’s **View** button is clicked. To display the others directly within Uwazi, locate the desired PDF from within the list of **Primary Documents** and click its white **View** button. [Learn more about creating entities](https://uwazi.readthedocs.io/en/latest/admin-docs/working-with-entities-in-your-collection.html#how-to-add-new-entities-to-the-library) with **Primary Documents** and **Supporting Files**.
:::

## OCR PDFs within Uwazi

Sometimes, text contained within a PDF is “locked” inside a digital image, meaning that we can’t directly work with it -- highlight it, copy and paste it elsewhere, annotate it, etc. You can convert it into machine-readable and searchable text using the Optical Character Recognition (OCR) functionality within Uwazi.

Step 1: Navigate to the **Settings** ![Settings icon](images/cog-solid.png) area and then click on **Collection**.

Step 2: Under **Services**, activate the **Document OCR Trigger** option and click on **Save**.

:::{note}
If you do not see this option in your collection’s settings and require this service, [contact us](how-to-report-bugs-or-problems-in-uwazi.md).
:::

Step 3: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity which holds the **Primary Document** (PDF) that you want to OCR. Click on the entity to expand the right sidebar and see more details about the entity. You will see the file name of the entity’s **Primary Document** alongside a label indicating the language of its contents (e.g. ```English```). Click the **View** button to see the document in full.

:::{note}
When non-OCRed documents are first uploaded as the Primary Document of an entity, Uwazi often labels the document’s language as Other because it cannot identify the language of the text. Consequently, a notice will appear in the top right of the document viewer that says **Unsupported OCR language**. For such documents, before initiating the OCR service, click the white **Edit** button next to the Primary Document’s file name and change the language from ```Other``` to the actual language of the document. Then click **Save**.
:::

Step 4: Within the document viewer, click on the **OCR PDF** button on the top right. The button will then change to say **In OCR Queue** while Uwazi is processing the document. Depending on the size and length of the document, the process could take anywhere from a few seconds to a few minutes. Once the process has finished, the status will change to say **OCR ✔**.

:::{note}
After the OCR process has finished, the original document that was uploaded to the entity will be placed in the **Supporting Files** section of the entity, while the new OCRed document will be added to the **Primary Documents** section with a filename that is prefixed with OCR. You are free to keep the original file attached as a **Supporting File** or delete it from the entity completely, according to your preference.
:::

## Configuring and using the filters sidebar in the Library

**Filters** appear on the right sidebar of the **Library** ![Library icon](images/image_0.png). Mixing and matching different filters can help you to quickly navigate your Uwazi collection. The **Filters** sidebar also acts as a sort of dashboard for the data in your collection, displaying aggregates of the different types of entities and different properties that they contain.

As you toggle on and off different filters, the figure that is displayed alongside each filter will update to indicate how many entities in total share the criteria that you have applied. This can be a simple yet useful way to answer basic questions about the contents of your collection. For example, how many entities of a certain type are there? Or what is the most or least common property associated with a certain type of entity?

There are a few types of filters. For users with login credentials to an Uwazi collection, there are two sets of blue filters that refer to the visibility and permissions settings of different entities:

- **Restricted** means that only a selected subset of users are able to see and/or edit an entity, whereas **Published** means that everyone who has access to the collection is able to see an entity.

- **Shared as viewer** means your individual user account or a specific user group to which you belong has been given explicit permission to see an entity, whereas **Shared as editor** means your individual user account or a specific user group to which you belong has been given explicit permission to edit an entity

:::{tip}
[Learn more about working with entities in the Library](working-with-entities-in-your-collection.md#understanding-view-and-edit-permissions-for-entities).
:::

There are also two different types of filters that refer to the entity templates and properties utilised in your collection: **Primary Filters** and **Secondary Filters**.

### Configure primary filters

The **Primary Filters** are derived from the types of entity templates that exist in your collection. You can define which ones can be used as filters in the **Library**’s ![Library icon](images/image_0.png) sidebar, customize the order in which the filters appear, and group certain ones together under a label of your choosing.

Step 1: Navigate to the **Settings** ![Settings icon](images/cog-solid.png) area and then click on **Filters**.

Step 2: Click on **Add entity type**, in the pop-up that displays select those that you want to use as filters and click **Add**.

Step 3: If you would like to group certain filters together, click on the **Add group** button. Give the group a descriptive label and add the entity types that you would like to appear in the group.

Step 4: Once finished, **Save** the changes you have made. You can now go to the **Library** and view the primary filters you have configured.

### Configure secondary filters

Besides using the types of templates as filters, you can also select which specific properties on the entities act as filters. These are known as **Secondary Filters**.

Step 1: Click on the **Settings** ![Settings icon](images/cog-solid.png) icon and then click on **Templates**.

Step 2: Select the **Edit** button on the type of template you would like to edit.

Step 3: Find the property that you want to include as a filter in the **Library** and click on the **Edit** button.

Step 4: Select whichever filter options match your needs:

- **Use as filter**: This checkbox activates the ability to filter entities according to this property. When someone visits the **Library** and selects the corresponding type of template among the **Primary Filters** in the **Library**’s sidebar, the option to further filter all of the entities by this property will then appear.
- **Default filter**: This additional option makes it so the property always shows as a filter in the **Library**’s sidebar by default, no matter if the corresponding type of template among the **Primary Filters** is selected or not.
- **Show in cards**: While not technically a filter, this additional option makes it so the property appears in the entity card within the **Cards view**. Selecting this option on a few key properties can make it easier to quickly skim through the **Library** by sight and identify specific entities.

Step 5: Click on **Save**. You can now go to the **Library** ![Library icon](images/image_0.png) and view the filters you have configured.

### Using the filters sidebar

While using the filters sidebar in the **Library** ![Library icon](images/image_0.png) to explore your entities, there are a few additional options available that can enhance your results.

Next to the Primary Filters, you will see a **FEATURED/ALL** toggle in the sidebar:

- Using the FEATURED operator will display only templates that you have explicitly configured as Primary Filters.

- Using the ALL operator will display a list of every template that exists in your collection, including the templates you haven’t configured as Primary Filters.

Next to any **Select** properties with multiple select configured that you have set as filters, you will see an **AND/Or** toggle next to the filter:

- Using the **AND** operator will display the entities that contain all the properties for which you are filtering.

- Using the **OR** operator will display the entities that contain at least one of the properties for which you are filtering.

For **Select** properties which utilise **Thesauri** with terms organised into groups, you will notice three different possible configurations when using them as filters in the sidebar:

- Clicking on a group name will select all of the terms contained within the group, resulting in a green checkmark next to the group’s name as well as next to all of the corresponding terms.

  - For example, imagine a group named Asia which contains the terms ```Bangladesh```, ```Cambodia``` and ```India```. If you click on ```Asia```, the terms ```Bangladesh```, ```Cambodia``` and ```India``` will be selected and consequently, all entities that match these filters will appear in the Library.

- Clicking on the group name will select all of the terms contained within the group. However, you are free to deselect individual terms within the group. This will result in a green line next to the group’s name and a green checkmark next to only those terms that you want to apply as filters.

  - For example, imagine a group named Asia which contains the terms ```Bangladesh```, ```Cambodia``` and ```India```. If you click on ```Asia```, the terms ```Bangladesh```, ```Cambodia``` and ```India``` will all be selected. You can uncheck ```Cambodia```, and consequently only entities that match the ```Bangladesh``` and ```India``` filters will appear in the Library.

- Clicking on the group name twice will result in a green box next to the group’s name and check-marks next to all of the terms contained within it; however, the terms will be grayed out and you will be unable to deselect individual terms. This action selects the group as a unit and creates a URL for the filtered entities that will automatically incorporate any additional terms that are added later on to the group.

  - For example, imagine a group named ```Asia``` which contains the terms ```Bangladesh```, ```Cambodia``` and ```India```. Now imagine that you need a link to only entities in your Library that have something to do with ```Asia```. Double click on ```Asia``` in the filters sidebar and the terms ```Bangladesh```, ```Cambodia``` and ```India``` will all be selected, and the browser will display a URL for this subset of your entities. If later on you expand the ```Asia``` group and add ```Myanmar```, you can use the same URL as before to see only entities in your Library that have something to do with ```Asia``` – entities that match the ```Myanmar``` filter will be displayed alongside ones that match the ```Bangladesh```, ```Cambodia``` and ```India``` filters.

## How to search within your collection

There are a few different types of search that you can conduct in your Uwazi collection.

### Search the entire collection

You can perform a search using the search bar found along the top of the **Library** area ![Library icon](images/image_0.png). It can be a generic text search, which will show any terms mentioned in the search query. Or you can search for a specific word or phrase by enclosing it in quotation marks to find the exact match (e.g.```"United Nations Committee on Enforced Disappearances"```).

### Search only within a particular document

You can also perform a search within PDFs that are uploaded as the **Primary Document** of an entity. [Learn more about adding Primary Documents](working-with-entities-in-your-collection.md#how-to-directly-add-pdfs-to-the-library).

Step 1: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity that contains the document you want to search. Click the **View** button to see the document in full.

Step 2: Click on the **Search** ![Search icon](images/fa-search.png) icon in the right sidebar. A search bar will appear.

Step 3: Input your search query. All of the mentions within the document of the word or phrase you searched for will appear in chronological order.

Step 4: Click on any of the search results to be taken to the specific segment of the document.

### Advanced search queries

To make your search queries more targeted, you can use several different advanced techniques:

- An asterisk ```*``` added to a query will conduct a **Multiple Character Wildcard Search**. The asterisk stands in for any number of characters in your query. For example, a search for ```juris*``` will match words such as jurisdiction, jurisdictional, jurists, jurisprudence, etc.
- A question mark ```?``` added to a query will conduct a **One Character Wildcard Search**. The question mark stands in for one single character only. For example, ```198?``` will match any of the years between 1980 and 1989 as well as 198a, 198b, etc.
- Quotation marks enclosing a query like this ```“...”``` will conduct a search that looks for **Exact Term Match**. For example, ```"Costa Rica"``` will return different results compared to ```Costa Rica``` without quotation marks.
- A tilde ```~``` added after a phrase in quotation marks will conduct a **Proximity Search**. The tilde indicates that you want to look for results that match your query approximately, but not exactly. You can accompany the tilde with a number to set a maximum number of words that separate the original terms in your query. For example, ```“the status”~5``` will find anything having “the” and “status” within a distance of 5 words, such as “the procedural status” or “the specific legal status”.
- ```AND```, ```OR``` and ```NOT``` added to a query will conduct a **Boolean Search**. ```AND``` indicates that all words searched for must be present; ```OR``` indicates that only one of the words searched for must be present; and ```NOT``` excludes results that contain the word included. For example, ```status AND women NOT Nicaragua``` will match anything that contains both the words status and women and does not contain the word Nicaragua.

:::{tip}
Refer to Elasticsearch’s [query string syntax page](https://www.elastic.co/guide/en/elasticsearch/reference/5.5/query-dsl-query-string-query.html#query-string-syntax) for more information on search options.
:::

## How to sort entities in the Library

Whether you have applied filters, have conducted a keyword search, or are looking at the collection in its entirety, you can sort entities that are shown in the **Library** ![Library icon](images/image_0.png) according to different criteria by using the dropdown list located beneath the search bar. Default sorting options include:

- By entity title, in alphabetical order or reverse alphabetical order
- By date the entity was added to the collection, from newest to oldest or from oldest to newest
- By date the entity was modified, from newest to oldest or from oldest to newest

You can add more criteria to the default options by utilising the **Priority sorting** checkbox when configuring properties on a template. [Learn more about creating templates](building-info-architecture.md#how-to-create-templates).

## How to create a table of contents

Within Uwazi, you can create an interactive **Table of Contents** for a PDF that is uploaded to an entity as a **Primary Document**, which will make it easier to quickly navigate through its contents. You can access it by clicking on the **Table of Contents** icon in the right sidebar of an entity.

Step 1: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity that contains the document for which you want to create a **Table of Contents**. Click the **View** button to see the document in full.

Step 2: Within the document, use the cursor to highlight the text that you want to add as the first heading in the table of contents. Three buttons will appear.  Click on **Add to table of contents**, and the highlighted text will appear on the right sidebar.

:::{note}
You may need to make small edits to the heading, such as restoring spaces between words.
:::

Step 3: Repeat this process until you have created a full **Table of Contents**. You can add as many headings and subheadings as you like. You can nest subheadings under headings by clicking on the arrow buttons to the left of the table of content entries. Uwazi currently supports six degrees of such indentations; each is styled differently to improve readability.

Step 4: Once you have finished, click **Save**. The **Table of Contents** will now be accessible to anyone who views the document. Clicking on any heading will jump to its respective section of the document. If you ever need to revise or add more contents in the future, simply click the **Edit** button.

## How to create References

In Uwazi, a **Reference** connects selected content in a **Primary Document** to other selected content within the same document, to other selected content in a different **Primary Document**, or to an entity (which may or may not have a **Primary Document** attached). You can see all of the **References** that a document has by clicking on the **References** icon ![References icon](images/image_54.png) in the right sidebar of its entity. Before you can configure a **Reference**, you must first create the **Relationship Type** that will describe the nature of the **Reference**.

### How to create relationship types

Step 1: Navigate to the **Settings** area and click on **Relationship types**.

Step 2: Click on the **Add relationship type** button. Give the relationship a descriptive name.

:::{note}
You will also see the **Add relationship type** button as an option when editing an entity template. Here, you can quickly create, name and save a **Relationship Type**. Later on, if you navigate to the **Settings** area  and click on **Relationship types**, you will see it listed there.
:::

Step 3: Click **Save**.

### Reference other text in the same or a different document

Step 1: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity that contains the document for which you want to create a **Reference**. Click the **View** button to see the document in full.

Step 2: Within the document, use the cursor to highlight the text to which you want to add a **Reference**. Three blue buttons will appear. Click on the **Connect to a paragraph** button and an area called **Create Reference** will open in the right sidebar.

Step 3: Using the checkboxes, select the previously defined **Relationship Type** that you would like to use as part of this **Reference**.

Step 4: Choose the document from the list which contains the text to which you want to make the **Reference**. If the list is long, you can use the search to locate the document more quickly. You are free to select the same document that you are currently editing.

Step 5: Click the green arrow button to proceed. You will then be taken to the document you have selected. Using the cursor, highlight the text that you want to reference.

Step 6: Click the **Save** button. The referenced text in both documents will be highlighted in yellow, indicating that it is associated with a **Reference**. Clicking on the document icon shown alongside the reference in the right sidebar will take you to the related paragraph.

### Reference another entity (with or without a Primary Document)

Step 1: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity that contains the document for which you want to create a **Reference**. Click the **View** button to see the document in full.

Step 2: Within the document, use the cursor to highlight the text to which you want to add a **Reference**. Three buttons will appear. Click on the **Connect to a document** button and an area called **Create Reference** will open in the right sidebar.

Step 3: Using the checkboxes, select the previously defined **Relationship Type** that you would like to use as part of this **Reference**.

Step 4: Choose the entity from the list that you want to refer to. If the list is long, you can use the search bar to manually search by title to locate it more quickly.

Step 5: Click the green **Save** button. The referenced text will be highlighted in yellow, indicating that it is associated with a **Reference**. Clicking on the document icon shown alongside the reference in the right sidebar will take you to the related entity.

## How to create Relationships between entities in the Information Hub

In Uwazi, a **Relationship** connects two or more entities in your collection so that it’s possible to scrutinise how they interact with one another. You can establish a **Relationship** in a consistent and structured way by adding a **Relationship** property to an entity template. Whenever a new entity is created using the template, the **Relationship** metadata is subsequently displayed alongside the entity’s other properties. [Learn more about creating templates](building-info-architecture.md#how-to-create-templates).

However, you don’t have to predefine a relational model upfront or follow a rigid structure. Uwazi allows you to arbitrarily create **Relationships** between entities on a one-to-one basis or on a one-to-many basis. These **Relationships** are displayed in a tree called an **Information Hub**.

You can see an entity’s **Information Hub** with all of its **Relationships** by clicking on an entity in the **Library**, clicking on the **Relationships** icon ![Relationshipd icon](images/image_59.png) in the sidebar, and clicking the **Collapse all** or **Expand all** buttons at the bottom of the screen to see more detail. You can also access the full view of the **Information Hub** by clicking the **View** button on an entity and then clicking on the Relationships icon ![Relationship](images/image_59.png).

:::{note}
We sometimes use the term **Connection** to mean **Relationship**. In practice, these refer to the same feature.
:::

Before you configure a **Relationship**, you likely will first want to create a **Relationship Type** that will describe the nature of the **Relationship**. Otherwise, the relationship will be defined as "No label". See the section above on [how to create relationship types](#how-to-create-relationship-types).

### Create Relationships between entities in the Information Hub

Step 1: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity for which you want to create a **Relationship**. Click the **View** button to see the entity in full.

Step 2: Within the right sidebar, click on the **Relationships** icon ![Relationships icon](images/image_59.png) to open up the **Information Hub**. Then near the bottom of the screen, click on the **Edit** button.

Step 3: To start building the **Relationship**, click on the **New relationships group** button on the left side of the **Information Hub**.

Step 4: Using the dropdown list on the left side, select one of the previously defined **Relationship Types**. Whichever you choose should appropriately describe the role that the current entity plays in this **Relationship**. Alternatively, you can leave the **Relationship** without a label ("No label").

Step 5: Moving to the right side of the **Information Hub**, use the dropdown to once again select one of the previously defined **Relationship Types**. Whichever you choose should appropriately describe the role that the other entity plays in this **Relationship**. Alternatively, you can leave the **Relationship** without a label ("No label").

Step 6: Remaining on the right side of the **Information Hub**, click the **Add entities / documents** button. Then, within the right sidebar select the entity from the list that should form the other half of this **Relationship**. If the list is long, you can use the search bar to manually search by name to locate it more quickly.

Step 7: You can add more entities to this **Relationship** by repeating the same process as above.

Step 8: Once you have finished, click **Save**.

### Edit Relationships in the Information Hub

Step 1: Navigate to the **Library** ![Library icon](images/image_0.png) and locate the entity whose **Relationships** you want to edit. Click the **View** button to see the entity in full.

Step 2: Within the right sidebar menu, click on the **Relationships** icon ![Relationships icon](images/image_59.png) to open up the **Information Hub**.

Step 3: Click on the **Edit** button. You can change the **Relationship Type** labels or remove a **Relationship** altogether by clicking on the **Delete** button.

Step 4: Click **Save** when you have finished.
