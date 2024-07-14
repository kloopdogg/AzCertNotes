# Facial Recognition
Use algorithms to locate and analyze human faces in images or video content.

## Uses of Facial Recognition
Uses of face detection and analysis
There are many applications for face detection, analysis, and recognition. 

- Security - face as ID
- Social media - tagging friends
- Intelligent monitoring - monitor facial expressions or eyes for alertness
- Advertising - find appropriate demographic audience
- Missing persons - find faces in images and videos
- Identity validation - ports of entry permit check

## Understand Face analysis
Another application of facial analysis is to train a machine learning model to identify known individuals from their facial features. This is known as facial recognition, and uses multiple images of an individual to train the model. This trains the model so that it can detect those individuals in new images on which it wasn't trained.

Azure Resource: **Azure AI Face** \
Tool: **[Azure Vision Studio](https://portal.vision.cognitive.azure.com/)** 

## Getting Started with Face Analysis
Azure provides multiple Azure AI services:
- **Azure AI Vision**, which offers face detection and some basic face analysis, such as returning the bounding box coordinates around an image.
- **Azure AI Video Indexer**, which you can use to detect and identify faces in a video.
- **Azure AI Face**, which offers pre-built algorithms that can detect, recognize, and analyze faces.

Use the Face service to:
- Detect the location of faces in an image.
- Determine if a person is wearing glasses.
- Determine if there's occlusion, blur, noise, or over/under exposure for any of the faces.
- Return the head pose coordinates for each face in an image.

Limited access policy, once approved, also allows:
- Comparison of faces for similarity
- Identify named individuals

Also detect attributes like:
- Accessories
- Blur
- Exposure
- Glasses
- Head pose
- Mask
- Noise
- Occlusion

