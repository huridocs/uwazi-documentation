# Extract metadata information from documents

## Overview

### Introduction

The metadata extraction tool is designed to help you quickly identify, retrieve, and save key details from PDF documents, such as titles, dates, keywords, and other essential information. Powered by machine learning, this tool automates much of the extraction process, saving you time and making it easier to analyze large sets of documents. Whether your focus is on case studies, witness statements, or legal reports, this tool eases the process of data extraction, so you can spend more time to drive advocacy and support your objectives.

### How it works

The metadata extraction tool uses machine learning models trained on a vast collection of documents to recognize patterns and extract relevant information. It scans your documents, breaks down the content into smaller segments, like words or phrases, and uses the patterns it learned during training to identify which sections of the document contain useful information. The models learn to do this by being trained on large amounts of sample data, known as training data, which includes examples of documents with labeled information. This allows the models to recognize similar patterns in future documents.

The effectiveness of this process is measured by accuracy, which refers to how often the models correctly identify and extract the right information. While the models strive for high accuracy, their performance can vary depending on factors like document formatting, clarity of text, and how closely the content matches the data the models were trained on. Over time, the models can be improved with more training data, enabling them to handle a broader range of document types and complex layouts.

### Limitations

While the machine learning models used for metadata extraction are powerful, they do have limitations. The accuracy of extraction depends on how similar your documents are to those the models were trained on. If your documents have unusual formats, inconsistent language, or unique content, the system may require human intervention to ensure correct details are extracted. Additionally, complex or heavily unstructured documents, like lengthy legal narratives, may require more manual review after extraction. Therefore, while this tool is effective, it’s best used alongside human validation, especially for sensitive or detailed work.

### Prerequisites

Before using the metadata extraction tool, there are a few prerequisites to consider. These include access to the tool, the type of data it works with, and your familiarity with the document content you want to extract.

- **Access**: This tool is in the beta phase and isn’t activated automatically for all Uwazi instances. Contact us if you’d like to access it during this phase. Note that when activated, the tool is only accessible to users with the roles of admin or editor.

- **Available data**: The tool currently works with PDF documents and can extract information to specific template properties. Supported properties include text, numeric, date, single select, multiple select, and relationship. Your instance should have appropriate templates with documents available for metadata extraction.

- **Knowledge of document content**: It’s important to have a clear understanding of the kind of information you want to extract, such as specific properties or categories relevant to your documents. This preparation will help ensure a smooth and accurate extraction process.

## How to use metadata extraction effectively

This step-by-step guide will walk you through the process of extracting metadata from your documents. Start by initiating the metadata extraction process, where you'll select the relevant properties from the available templates. The tool will then analyze the documents and generate suggestions for the extracted metadata. As you review these suggestions, you can accept those that are accurate and make any necessary adjustments to improve the results. By following these steps, you help ensure that the extracted metadata is both precise and meaningful.

### Creating a metadata extractor

Step 1: Go to **Settings** ![Settings icon](images/cog-solid.png) and select **Metadata Extraction**.

Step 2: Click on **Create Extractor**.

Step 3: In the dialog window that appears, enter a name for the extractor in the input field. Choose a descriptive name that makes it easy to identify the type of information you are extracting.

Step 4: From the list of available templates and properties (only those that qualify for extraction will be shown), select the property to use for metadata extraction, then click **Next**.

Step 5: Review your selections and click **Create**.

Once the system generates the extractor, it will appear in the table with its name, selected property, and associated templates.

### Reviewing suggestions

After creating a metadata extractor, it will be visible in the table listing all previously created extractors. The next step is to review the suggestions generated by the system. To do this, select **Review** in the corresponding table row to open the interface for reviewing suggestions from the selected metadata extractor.

A table with the following columns will be displayed:

1. Selection checkbox: The first column contains checkboxes that allow you to select one or multiple rows. These checkboxes can be used for bulk actions (currently available: **Accept suggestion**) on the selected items.

2. **Group** button: If the input property for the metadata extractor was a multi-select or relationship field, and there are multiple suggestions per document, they will be grouped together under the relevant document. The **Group** button allows you to expand or collapse these grouped suggestions.

3. **DOCUMENT**: This column lists the identifiers of the documents being processed by the metadata extractor.

4. **CONTEXT**: Displays a snippet of text from the document that is relevant to the generated suggestion(s).

5. **CURRENT VALUE/SUGGESTION**: This column shows both the current value of the relevant property and the system’s generated suggestion. If suggestions are grouped, a summary is displayed, including:

    - The number of existing values for the property (e.g., "2 values").

    - The number of suggestions generated by the system (e.g., "2 suggestions").

    - The status of the suggestions, such as matches (e.g., "1 matching" in green) or mismatches (e.g., "1 mismatching" in red).

6. Suggestion status: Initially, an orange **Accept** button is shown, allowing you to review and confirm the suggestions. Once accepted, a checkmark symbol will be displayed.

7. **Open PDF**: This button is available for each document, enabling you to open the original PDF for detailed review, where you can accept or correct the suggestion(s).

While reviewing suggestions, it’s best to accept the correct ones and correct any that are inaccurate. This feedback helps the system learn and improve its performance over time. The next section provides guidance on using the PDF viewing panel, which appears when you select **Open PDF** in a table row, to correct the system’s suggestions.

### Correcting suggestions

The PDF viewing panel is displayed on the right side of the window and is divided into two sections:

1. The upper section shows the PDF document.

2. The lower section displays the relevant property and its value(s). The interface and available options in this lower section vary depending on the property type.

#### Text, numeric, and date properties

For text, numeric, or date properties, the lower section shows the property name followed by an input field containing the current value. You can highlight any text in the PDF document and select **Click to Fill** to automatically update the property value with the highlighted text. This action also labels the highlighted portion of the document, which helps improve the machine learning model over time. If needed, you can remove the label from the document by clicking **Clear**. Once you’ve made your corrections, click **Accept** to save the updated value for the property.

#### Single select, multiple select, and relationship properties

For single select, multiple select, or relationship properties, the lower section displays the property name followed by a list of available values. You can choose to view all available values with the **All** filter or only the currently selected values using the **Selected** filter. Additionally, you can search for a specific value using the search bar. The **Select & Search** toggle button allows you to highlight text in the document, which then triggers an automatic search for matching values. This makes it quick and easy to find and select the appropriate values. Once you’re satisfied with your selection, click **Accept** to save the chosen values for the property.

### Retraining the system for improved suggestions

After reviewing and accepting or correcting several of the system’s suggestions, it’s recommended to retrain the system with this new input. Retraining allows the system to learn from your adjustments, resulting in more accurate and relevant suggestions for future extractions.

To initiate retraining, click **Find suggestions** at the bottom of the page. The system will then update you as it progresses through steps like "Sending label data...," "Training model...," and "Finding suggestions... x/y." The duration of this process depends on the number of documents involved, but you don’t need to wait for it to fully complete. As soon as the first new suggestions are ready, you can start reviewing them while the system continues generating more in the background.

You can repeat this retraining process as needed to refine the accuracy of the system’s suggestions. For optimal results, consider this iterative approach:

1. Create an extractor.
2. Label around 30-40 samples in the relevant documents.
3. Run **Find suggestions**.
4. Focus on reviewing suggestions where the model struggles, as correcting these will improve overall performance.
5. Repeat steps 2-4 until satisfied with the results.

## Closing remarks

By following the steps outlined in this guide, you can effectively use the metadata extraction tool to automate the process of identifying and organizing key information from your documents. The combination of machine learning and your input allows the system to continually improve, delivering more accurate results with each iteration. While the tool simplifies data extraction, your role in reviewing and refining suggestions is crucial for achieving the best results. With ongoing use and periodic retraining, you can ensure that the system evolves to better meet your specific needs, making your document management process more efficient and precise.
