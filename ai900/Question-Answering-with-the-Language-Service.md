# Question answering with the Language Service
Create a custom question answering knowledge base with Azure AI Language, and create a bot with Azure AI Bot Service that answers user questions.

## Intro
`Conversational AI` describes solutions that enable a dialog between an AI agent (i.e., bot) and a human.

`Question answering` is used to build bot applications that respond to customer queries.

## Language service and Azure Bot Service
Resources:
- **Azure AI Language**: custom question answering feature used to create a knowledge base of Q&A pairs that can be queried using natural language input.
- **Azure AI Bot Service**: framework for developing, publishing, and managing bots on Azure.

Tools: 
- [Azure AI Language Studio](https://language.cognitive.azure.com/)
- [Azure AI Language REST API or SDK](https://learn.microsoft.com/en-us/azure/ai-services/language-service/concepts/developer-guide?tabs=language-studio)

### Create a knowledge base (KB)
Questions and answers can be built with Language Studio:
- Generated from an existing FAQ document or web page
- Entered and edited manually

### Deliver KB to users
Create a custom bot by using the `Microsoft Bot Framework SDK`
- Controls conversation flow
- Integrates with your KB

