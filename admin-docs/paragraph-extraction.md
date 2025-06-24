# Extract paragraphs from documents

## Overview

### Introduction

The paragraph extraction feature automatically detects and extracts paragraphs from uploaded PDF documents. This eliminates the time-consuming and error-prone process of manually identifying key content. Extracted paragraphs are saved as structured entities with relevant metadata in your collection.

This feature is especially useful when you need to:

- Organize information from large documents
- Make specific paragraphs accessible and searchable as entities
- Reference individual paragraphs instead of entire documents
- Process and extract content in multiple languages

### How it works

Paragraph extraction uses text analysis technology to analyze the structure of your PDF documents. It identifies individual paragraphs by examining text layout, sentence patterns, and formatting cues. Each paragraph is then extracted and stored as a separate entity, linked to its source document through metadata. The system supports multiple languages.

### Limitations

This feature has some limitations. Extraction accuracy depends on document quality. Poorly scanned, low-resolution, or image-based PDFs are challenging because text embedded in images cannot be reliably extracted. Documents with complex layouts (multiple columns, tables, lists, or text boxes) may not be interpreted correctly. This can lead to extraction errors. Very large documents may also take longer to process.

### Prerequisites

Before using the paragraph extraction tool, consider the following prerequisites:

**Access:** This feature is not enabled by default for all Uwazi instances. Contact us if you’d like to use it. When activated, paragraph extraction is available only to users with admin or editor roles.

**Available data and configuration:** The tool works with PDF documents that have been uploaded to entities in your collection. The template used by these entities becomes the source template for paragraph extraction. Extracted paragraphs are saved as new entities using a target template. You must also configure relationship types to connect source documents with their extracted paragraphs.

**Language support:** The tool supports multiple languages, but can only extract paragraphs in languages that are configured in your Uwazi instance. To extract paragraphs in a new language, you must first add that language to your system settings.

## How to use paragraph extraction effectively

Follow these steps to extract paragraphs from your uploaded documents. First, create a paragraph extractor, then run the extraction process and review the results.

### Creating a paragraph extractor

Step 1: Go to **Settings** ![Settings icon](images/cog-solid.png) and select **Paragraph Extraction**.

Step 2: Click **Add extractor**.

Step 3: Select the target template. Choose from the available templates and click **Select**. Use the search box to filter templates if needed. Click **Next** to continue.

:::{note}
Only templates with at least one rich text property and one numeric property are available for selection.
:::

Step 4: Select the source template. Choose the template that stores your source documents and click **Select**. Use the search box to filter templates if needed. Click **Next** to continue.

:::{note}
Only templates that are not used as source in any other paragraph extractor and are not selected as target in this extractor are available for selection.
:::

Step 5: Configure extraction settings. Use the dropdown menus to define how paragraphs will be extracted, stored, and connected to source documents:

- **Paragraph text extraction property (rich text):** Select where the actual paragraph text will be stored. Choose from the available rich text fields in your target template.
- **Paragraph number extraction property (numeric):** Select where the paragraph number will be stored. Choose from the available numeric fields in your target template.
- **Target relationship type:** Define how the extracted paragraphs will relate to the source document. Select the appropriate relationship type from the dropdown.
- **Source relationship type:** Define how the source document will relate to the extracted paragraphs. Select the appropriate relationship type from the dropdown.

Once all fields are completed, click **Create**. Your new paragraph extractor will appear in the table showing the source and target templates, along with the number of source entities available for extraction.

### Extracting paragraphs

After creating your paragraph extractor, locate it in the **Extractors** list and click the **View** button next to it. This will take you to the paragraph extractor details page, where you can see all the entities that belong to the source template and contain documents for extraction. The paragraph extractor details page displays a table with the following information:

- **ENTITY**: The name of each entity that contains document(s) for extraction
- **LANGUAGE(S)**: Shows which languages were detected in the document(s) (e.g., EN for English, FR for French). Only languages configured in your Uwazi instance will be displayed.
- **PARAGRAPHS**: The number of paragraphs extracted from each document (0 if the entity has not been processed yet)
- **STATUS**: Shows the current processing status:

  - New: A new entity is detected and ready for paragraph extraction
  - Processing: Entity is currently being processed
  - Obsolete: A change in the source entity (e.g. adding or replacing a document) has made the extracted paragraphs obsolete, and the entity needs to be reprocessed
  - Error: An error occurred during extraction
  - Green checkmark: Extraction has been completed successfully

- **View** button: Click to see the extracted paragraphs from that specific entity

There are two ways to start the extraction process:

1. **Run extraction for all new entities**: Click the **Extract new paragraphs** button at the bottom left of the paragraph extractor details page. This will process all entities in the list that are marked as `New`.

2. **Run extraction for specific entities**: Select the entities you want to process by checking the boxes next to them. Then click the **Extract paragraphs** button at the bottom left of the paragraph extractor details page. This will process only the selected entities.

:::{warning}
Running the extraction process for selected entities will delete all previously extracted paragraphs for these entities and recreate them based on their current document(s). Any previously added metadata to the paragraphs will be lost. Continue only if you are sure you want to update the paragraphs.
:::

### Viewing extracted paragraphs

When you click the **View** button next to a processed entity, you'll see a detailed view of all extracted paragraphs from the document(s) of that specific entity. The view includes a table with the following columns:

- **PARAGRAPH #**: Sequential number showing the order of paragraphs in the document
- **LANGUAGE**: Shows which language was detected for each paragraph (EN for English, FR for French)
- **TEXT**: The actual extracted paragraph content
- **Group** button: Click to expand or collapse a specific paragraph group. Each paragraph group contains the specific paragraph in all available extracted languages. This allows you to see the same paragraph in different languages if available. By default, all paragraph groups are collapsed, showing the paragraph in the instance's default language.
- **View** button: Click to see additional details about the extracted paragraph in a panel on the right side of the screen from where you can also navigate to the related paragraph entity.

Click **Open PDF** in the top right to reference the original document in the default language while reviewing extractions to verify that paragraphs were extracted correctly. This interface allows you to quality-check the extraction results.

## Closing remarks

By following the steps outlined in this guide, you can effectively use the paragraph extraction tool to streamline your document processing workflow. This feature is designed to enhance your ability to manage and utilize large collections of documents by making individual paragraphs easily accessible and searchable, thus improving overall efficiency in handling textual data.
