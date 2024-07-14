# Azure AI Document Intelligence
**Document intelligence** describes AI capabilities that support `processing text and making sense of information in text`. 
- Extension of OCR
- Automates the process of extracting, understanding, and saving the data in text
- Replace slow and error-prone human-based processes

Resource: [Document Intelligence](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/?view=doc-intel-4.0.0) \
Tool: [Document Intelligence Studio](https://formrecognizer.appliedai.azure.com/studio)

## Capabilities of Document Intelligence
Document Intelligence relies on ML models trained to recognize data in text. 

**Document analysis**: ability to extract text, layout, and key-value pairs, providing locations of text on a page identified by bounding box coordinates.

Challenges are natural as documents come in different formats. Custom ML models would be necessary to recognize unique formats.

## Features
Features grouped by model type:
- **Prebuilt models** - pretrained models for common document types
    - Invoices, business cards, ID documents
- **Custom models** - can be trained to identify specific fields that are not included in the existing pretrained models.
- **Document analysis** - general document analysis that returns structured data representations, including regions of interest and their inter-relationships.

Fields recognized include:
- Field names
- Data
- Confidence score

