---
title: AnythingLLM & APIpie Configuration Guide
sidebar_label: AnythingLLM
tags:
  - Chat Integration
  - Chat
keywords:
  - AnythingLLM Integration
  - APIpie Integration
  - AnythingLLM API
  - APIpie API
  - ChatGPT Alternative
  - Chat GPT Alternative
  - Chatbot Integration
  - AI Integration
  - LLM API
  - OpenAI Alternative
  - Openai Integration
  - AI Chatbot
  - AI Models Integration
  - API Integration Guide
  - ANSE Integration
  - Conversational AI Integration
  - AI Assistant Integration
  - AI Service Integration
  - API Integration for AI
  - Neuronic AI Integration
  - AI Chat API
  - AI Model Integration
  - AI Integration Platform
  - AI Application Integration
  - AI Solutions API
  - APIpie AI Integration
  - ANSE and APIpie
  - AI Development API
  - AI Chat Framework
  - AI Assistant API
  - AI Integration Tutorial
  - Integrate ANSE with APIpie
  - API Integration Documentation
  - APIpie Chatbot
  - AI Integration Steps
  - AI Integration Best Practices
  - AI Integration Tools
  - AI Integration Services
  - AI Integration Benefits
  - APIpie Chatbot Integration
sidebar_position: 2
---

::div{align="center"}
![APIpie](/docs/img/apipie-logo.png){'20px'="" }}="" height="125" marginright:="" style="{{" width="125"} ![AnythingLLM](/docs/img/AnythingLLM.png){height="125" width="497"}
::

This guide will walk you through the process of integrating AnythingLLM with APIpie to leverage the power of multiple AI models and enhance your chatbot experience.

## Steps

### 1. Create an Account

- **Link**: [Register here](https://apipie.ai/dashboard/auth/register)
- Follow the link and fill out the form to create your account.

### 2. Add Credit

- **Link**: [Add Credit](https://apipie.ai/dashboard/profile/subscribe)
- Access the subscription section after logging in to add credits to your account.

### 3. Generate an API Key

- **Link**: [Generate API Key](https://apipie.ai/dashboard/profile/api-keys)
- Navigate to the API keys section and create a new key. This key is necessary for API requests.

### 4. Install AnythingLLM

- Follow the [AnythingLLM Installation Guide](https://docs.useanything.com/installation/overview) to install either locally or via Docker

### 5. Access the AnythingLLM Settings

- Configure the LLM Preference either on initial setup or by changing the settings after configured.
- Find your prefered LLM on the [APIpie.ai Dashboard](https://apipie.ai/dashboard/) and take note of the Name, MAxTokens, and MaxResponse.
- Set the "Base URL" to <https://apipie.ai/v1/>
- Paste your generated API key into the designated field.
- Configure the appropite model name.
- Set the "Token Context Window" to the "MaxResponse".
- Set the "Max Tokens" and save the settings.

#### Initial Setup:

::div{align="center"}
![Initial Setup](/docs/img/Integrations/AnythingLLM/Initial-Settings.png)
::

#### Changing Settings:

::div{align="center"}
![Settings](/docs/img/Integrations/AnythingLLM/Settings.png)
::

### 6. Set the AnythingLLM Agent LLM

#### Agent Setup:

- From the main screen select the settings option on the configured workplace
- Change to the "Agent Configuration" tab.
- Select "Local AI" as the provider

::div{align="center"}
![Agent Setup](/docs/img/Integrations/AnythingLLM/Workplace-Agent.png)
::

#### Agent AI Settings:

- Set the "Local AI Base URL" to <https://apipie.ai/v1>
- Enter your generated API key ( if you want separate activity statements generate a new key identifying the agent)
- Save Settings

::div{align="center"}
![Agent AI](/docs/img/Integrations/AnythingLLM/Local-AI-Agent.png)
::

- Select the desired Agent AI model.

### 7. Start Chatting

- With the integration complete, you can now enjoy AI-powered conversations in AnythingLLM.

::div{align="center"}
![Desktop](/docs/img/Integrations/AnythingLLM/AnythingLLM.png){'20px'="" }}="" height="502" marginright:="" style="{{" width="845"}
::

## Caveats

- Currently AnythingLLM is yet support APIpie TTS, STT, or Embedding.
- If this changes or if assistance is required to onboard more APIpie features please reach out on our [Discord](https://discord.gg/hs82THc9Tw)

## Additional Resources

- **AnythingLLM Website**: Explore more features and capabilities of AnythingLLM. [Visit the website](https://useanything.com/)
- **AnythingLLM GitHub**: Access the source code and contribute to the AnythingLLM project. [Visit GitHub](https://github.com/Mintplex-Labs/anything-llm)
- **AnythingLLM Documentation**: Dive deeper into AnythingLLM's functionalities and configurations. [Access the docs](https://docs.useanything.com/)
- **Mintplex Labs**: Explore Mintplex Labs the team that brings us AnythingLLM [Mintplex Labs](https://mintplexlabs.com/)

## Connect with AnythingLLM

- [LinkedIn](https://www.linkedin.com/company/mintplex-labs)
- [YouTube](https://www.youtube.com/@mintplexlabs)
- [Twitter/X](https://x.com/AnythingLLM)
- [Discord](https://discord.gg/Dh4zSZCdsC)

### Additional Support

If you encounter any issues during the integration process, please reach out to us on [Discord](https://discord.gg/hs82THc9Tw) for assistance.
