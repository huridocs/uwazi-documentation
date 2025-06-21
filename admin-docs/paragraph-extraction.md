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

### Creating a paragraph extractor

### Viewing extracted paragraphs
