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

**Available data and configuration:** The tool works with PDF documents that have been uploaded using a source template. Paragraphs are extracted and saved using a target template. Your system must have a relationship type configured to connect source documents with their extracted paragraphs.

**Language support:** The tool supports multiple languages, but can only extract paragraphs in languages that are configured in your Uwazi instance. To extract paragraphs in a new language, you must first add that language to your system settings.

## How to use paragraph extraction effectively

Follow these steps to extract paragraphs from your uploaded documents. First, create a paragraph extractor, then run the extraction process and review the results.

### Creating a paragraph extractor

To create a paragraph extractor:

Step 1: Go to **Settings** ![Settings icon](images/cog-solid.png) and select **Paragraph Extraction**.

Step 2: Click **Add extractor**.

Step 3: Select the target template. Choose from the available templates and click **Select**. Use the search box to filter templates if needed. Click **Next** to continue.

:::{note}
Only templates with at least one rich text property and one numeric property are available for selection.
:::

Step 4: Select the source template. Choose the template that stores your source documents and click **Select**. Use the search box to filter templates if needed. Click **Next** to continue.

:::{note}
Only templates that are not used as source in any other extractor and are not selected as target in this extractor are available for selection.
:::

Step 5: Configure extraction settings. Use the dropdown menus to define how paragraphs will be extracted, stored, and connected to source documents:

- **Paragraph text extraction property (rich text):** Select where the actual paragraph text will be stored. Choose from the available rich text fields in your target template.
- **Paragraph number extraction property (numeric):** Select where the paragraph number will be stored. Choose from the available numeric fields in your target template.
- **Target relationship type:** Define how the extracted paragraphs will relate to the source document. Select the appropriate relationship type from the dropdown.
- **Source relationship type:** Define how the source document will relate to the extracted paragraphs. Select the appropriate relationship type from the dropdown.

Once all fields are completed, click **Create**. Your new extractor will appear in the table showing the source and target templates, along with the number of source entities available for extraction.

### Viewing extracted paragraphs
