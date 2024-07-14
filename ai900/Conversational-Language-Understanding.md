# Conversational language understanding

Create applications that understand language with Azure AI Language.

Core concepts:
- Utterances
    - Phrases (e.g., Turn on the lamp)
- Entities
    - Objects (e.g., lamp)
- Intents
    - Actions (e.g., TurnOn)
    - You should consider always using the None intent to help handle utterances that do not map any of the utterances you have entered. 
    - The None intent is considered a fallback, and is typically used to provide a generic response to users when their requests don't match any other intent.

## Authoring a model
Authoring a model involves `defining entities, intents, and utterances`. Then use that model for `predictions`.

> Generating predictions involves publishing a model so that client applications can take user input and return responses.

Authoring can be done in **Language Studio**.

## Training the model
Training is the process of `using your sample utterances to teach your model` to match natural language expressions that a user might say to probable intents and entities.

## Predicting
Publish your Conversational Language Understanding application to a prediction resource for consumption.

- Client applications use the model by connecting to the endpoint (with auth key).
- Submit user input to get predicted intents and entities.
- The predictions are returned to the client application, which take appropriate action based on the predicted intent.