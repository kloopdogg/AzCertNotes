# Optimal Character Recognition

**Optical character recognition (OCR)** is the capability for artificial intelligence (AI) to process words in images into machine-readable text.

Uses:
- Automate text processing 
    - Improve the speed and efficiency
    - Remove need for manual data entry 
- Recognize printed and handwritten text 
    - Note taking
    - Digitize medical records 
    - Scan checks or forms

## Azure AI Vision
AI Vision is where computer vision intersects with natural language processing.
- Vision capabilities to "read" the text
- NLP to make sense of it

Azure Resource: **Azure AI Vision** \
Tool: **[Azure Vision Studio](https://portal.vision.cognitive.azure.com/)** 

## Azure AI Vision's OCR Engine
**Read API**, otherwise known as **Read OCR engine**, uses the latest recognition models and is optimized for images that have a significant amount of text or have considerable visual noise.

Read API returns results, with bounding box coordinates, for:
- Pages
- Lines
- Words
