# TRANSLATING YOUR COLLECTION

An Uwazi collection can be made available in one language or in multiple languages. In fact, Uwazi supports the localisation of its interface and a collection’s entities into more than 180 different languages. This ranges from the world’s most commonly spoken languages such as Chinese, French, Hindi and Spanish, to less widespread but no less important languages such as Burmese, Kurdish, Quechua and Yoruba.

## How to configure the available languages for your collection

The first step to making your Uwazi collection multilingual is to enable your desired language options. When multiple languages are enabled for your collection, you will see the languages included as items in the main navigation menu of your collection.

It’s important to note that enabling a language does not mean that the interface of your collection or the contents of entities in the Library will automatically be translated into that language. The processes of translating the interface and contents are explained further along in this section.

To configure the available languages for your collection:

Step 1: Navigate to the **Settings** area and click on **Languages**.

Step 2: Locate the language(s) you want and click **Add language**. (If your language is not in the list, please get in touch with us.)

Step 3: Type **CONFIRM** (in all capital letters) in the confirmation dialog and click **Accept**.
- Note:  Search functionality within the Library will be limited for languages that aren’t supported by ElasticSearch. For further information, consult [ElasticSearch’s website](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-lang-analyzer.html).

Step 4: At the top of the page under **Active Languages**, select which language will be the default language for your collection.
- Except for the default language, you are free to delete languages from your **Active Languages** list. When you do, however, make sure that you are not currently navigating your Uwazi collection in the same language that you’re trying to delete. If you try to delete a language while the matching language option is toggled on within the main navigation menu, deletion will not work.

## How to translate the Uwazi interface 

The collective of buttons, menu items, system messages, etc. that you interact with while using the Uwazi software is called the interface.  The Uwazi interface is available by default in English, but it can be translated into any of the languages that you have previously enabled.

All interface translations that are currently configured in your instance can be consulted and edited at any time by navigating to the **Settings** area, clicking **Translations** and then clicking **User Interface**.

![](images/image_91.jpg)

### Translate interface terms in bulk with CSV import

The majority of Uwazi’s interface can be translated all in one go by importing a **Comma-Separated Values (CSV) file** that includes the list of terms in English and their corresponding translations. This method can be especially convenient when setting up your Uwazi instance for the first time.

A CSV file of the English-language interface terms is available for download on the Uwazi website. We also offer CSV files of already translated interface terms for the following languages: Arabic, French, Spanish and Russian.

To translate the Uwazi interface using CSV import:

Step 1: If you aren't already in possession of a CSV file containing the translated interface terms, then you must first create a CSV file on your computer. The first column within the file should be labeled “Key” and include the list of terms in English. Each term should occupy its own row.

Step 2: The next column should be labeled with the name of the target language, as written in English (e.g. “Russian”, “Spanish”, “Swahili”), and include the corresponding translations of the English-language terms. For example, here’s a sample CSV file viewed as plain text:

And here’s the same file viewed in a spreadsheet program:

Step 3: Save the **CSV file** in UTF-8 format on your computer.

Step 4: Navigate to the **Settings area**, click **Translations** and then click **User Interface**.

Step 5: Click the blue **Import** button. Using the file browser to navigate your computer’s storage, find and select the **CSV file**. Once the import has finished, the translations will appear on screen.

Step 6: Click the green **Save** button.

### Translate interface terms via the Live Translation feature

In Uwazi, you have the option to translate interface terms one by one as you encounter them while navigating the software. This feature, which is called **Live Translation**, allows you to see how a term is used in context. It can be useful for easily translating interface terms that are added to the software as part of newly released development or for quickly correcting an existing translation that isn’t quite right.

To use **Live Translation**: 

Step 1: When you encounter an interface term that you would like to translate, click on the **Translation** icon found in Uwazi’s main navigation menu. This activates **Live Translation**. All of the terms on the screen that are translatable will be underlined in orange.

Step 2: Click on the term that you want to translate, add its corresponding translation(s) , and click **Submit**. Repeat this process for any of the other underlined terms on the screen that you would like to translate.

Step 3: When you have finished, click on the **Translation** icon in the main navigation menu once more to deactivate **Live Translation**.

## How to translate the contents of your collection

An Uwazi collection is made up of **Entities**, which contain properties, can feature documents, and can have connections to one another. It might also feature Pages with important information or components like a contact form. It’s possible to translate the contents of your collection into any and all of the languages that you have previously enabled. This means that when you toggle from one language option to another using the links within the main navigation menu, the contents of the Library or a Page will consequently be presented in the language that corresponds to your selection.

There are four main aspects of translating the contents of your Uwazi collection:
- Translating the **Name** or **Label** of properties, **Thesauri**, **Relationship Types**, custom **Filters** and custom navigation menu items  
- Translating the contents of entity names and **Text**, **Rich Text**, **Image** and **Media** properties
Uploading translated **Primary Documents** and recreating **Table of Contents** and **References**
Translating custom **Pages**

### Translate the Name / Label of properties, Thesauri, Relationship Types, custom Filters and custom navigation menu items

Until you translate the various data labels that appear within an entity or around your collection  such as the Name or Label of properties, Thesauri terms, Relationship Types, custom Filters or custom navigation menu items, they will appear in their original language regardless of whichever language option is currently selected in the main navigation menu.

Step 1: Navigate to the **Settings** area and click **Translations**.

Step 2: Click on the entity template, **Thesauri**, **Relationship** (Connection), etc. which contains the data labels that you want to translate.

Step 3: Translate each term.

Step 4: When you have finished, click **Save**.

### Translate property names, thesauri values, relationship types, custom filters and custom navigation menu items

![](images/image_95.jpg)

Until you translate the various data labels that appear within an entity or around your collection r such as property names, thesauri values, relationship types, custom filters or custom navigation menu items, they will appear in their original language regardless of whichever language option is currently selected in the main navigation menu.

Step 1: Navigate to the **Settings** area and click **Translations**.
Step 2: Click on the template, thesauri, etc. that you want to translate.
Step 3: Translate each term.
Step 4: When you have finished, click **Save**.


### Upload translated Primary Documents

![](images/image_96.jpg)

Until you upload a translated version(s) of an entity’s Primary Document, it will appear in the original language regardless of whichever language option is currently selected in the main navigation menu.

Step 1: Navigate to the **Library** and locate the entity to which you want to upload a translated version of its **Primary Document**.

Step 2: Click on the entity to expand the right sidebar and see more details about the entity. You will see the file name of the entity’s **Primary Document** alongside a label indicating the language of its contents (e.g. English).

Step 3: Click the **Upload PDF** button and select the translated version of the Primary Document from within the file browser.

Step 4: Uwazi will automatically detect the language of the uploaded file and attach a corresponding label. If the language of an uploaded **Primary Document** matches a language that is enabled in your collection, then Uwazi will load it by default when that language option is selected in the main navigation menu.

For example, imagine that you have English and Spanish enabled in your collection, and that you have an entity with a Primary Document in English and a version in Spanish. When you navigate the English-language collection and click the **View** button on this entity, Uwazi will load the English-language version of Primary Document. If you switch to the Spanish-language collection and click the **View** button on this same entity, Uwazi will instead load the Spanish-language version of the Primary Document.

- **Note**: Uwazi is only able to automatically detect languages that are supported by ElasticSearch, and any other languages will be labeled as “Other”. For further information, consult ElasticSearch’s website.

### Translate Pages

Until you translate the contents of a Page, they will appear in their original language regardless of whichever language option is currently selected in the main navigation menu.

Step 1: Using the links within the main navigation menu, switch to the language into which you want to translate.

Step 2: Navigate to the **Settings** area and click **Pages**. Locate the Page that you want to translate and click **Edit**.

Step 3: Translate the contents of the Page. When you have finished, click **Save**.

## Managing translations over time

### Creating a new entity

Whenever you create and save a new entity or Page, all of its contents are synced across all of your collection’s available languages. If the entity has any Text, Rich Text, Image and Media properties or has a translated Primary Document, make sure to follow the previously explained process for translating them. Otherwise, they will appear in their original language regardless of whichever language option is currently selected in the main navigation menu.

### Edit an existing entity or Page

Whenever you edit the contents of an existing entity or Page, some changes will be synced across all of the languages of your collection, while others will not.

Changes made to the contents of the following will be automatically synced to all languages:
- Select and Multiselect properties
- Relationships
- Date, Date Range, Multi Date, Multi Date Range properties
- Geolocation property
- Numeric property
- Table of Contents of a Primary Document if the same source document is used in other languages (since it depends on the contents of the document)

Changes made to the contents of the following will not be automatically synced, so you will need to make any necessary updates in other languages manually:
- **Name** property
- **Text** property
- **Rich text** property
- **Media** property
- **Image** property
- **Pages**
