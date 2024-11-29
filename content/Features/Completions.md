---
title: Chat Completions Guide
sidebar_label: Completions
tags: [Chat, OpenAI Integration, Chat Models, GPT-4o]
keywords: [Chat Completions, OpenAI Integration, GPT-4o, Claude, AI Query Routing, API Usage,Chat Completions API, Conversational AI Integration, AI Chatbots API, OpenAI Compatible API, Chat Completion Endpoint, API Chat Integration, AI Content Generation API, Customer Support AI, Interactive AI Applications, AI Response Generation, Chat Completion Features, AI Messaging API, AI Assistant API, ChatGPT API Integration, AI Conversation API, AI Model Interaction, AI Chat Framework, AI Application API, API Chat Features, AI Assistant Integration, OpenAI API Compatible, Chatbot Development API, AI Messaging Features, AI Chatbot Solutions, AI Response API, Chat Completions Documentation, AI Integration API, AI Assistant Features, OpenAI API Integration, AI Chatbot API, AI Interaction API, AI Conversation API, AI Chat API, AI Response API, Chatbot AI API, Conversational AI API, AI Messaging Integration, AI Application Chat, AI Chatbot Endpoint, AI Chatbot Integration, AI Conversation Integration, AI Chat Functionality ]
sidebar_position: 3
---

<div align="center">
    <img src="/docs/img/Features/completions-banner.png" alt="Chat Completions Feature Banner" width="100%" />
</div>

Leverage the flexibility and power of our Chat Completions endpoint to integrate conversational AI into your applications. Whether you are building customer support bots, generating creative content, or crafting interactive experiences, our chat completion API is designed to help you get the most from AI models.

## Chat Completions Overview

The Chat Completions API allows developers to interact with AI models in a conversational manner by sending a sequence of messages to the model and receiving a response. The structure of these messages is fully compliant with OpenAI's API structure, allowing seamless integration.

### Open AI compatible framework

Just change the URL and your api key and your app built on Open AI API can now start using APIpie. Once you are using our API you can take advantage of all we have to offer.

## How Chat Completions Work

A typical API call sends an array of messages to the chosen model, where each message consists of a role (either `system`, `user`, or `assistant`) and content. The model then processes the conversation and returns a response based on the provided context. 

NOTE: 
- We use the chat completions route for all LLM interfaces, instruct, text, it doesnt matter, you can use them all via a single chat completion interface. 
- There is a different API interface for voice and image generation, it is also Open AI compatible format.

### Example API Call

Below is an example of how to use the Chat Completions API to generate a response:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "max_tokens": 100,
  "messages": [
    {
      "role": "user",
      "content": "Why is the sky blue?"
    }
  ]
}'
```

### Response Example

The expected response structure looks like the following:

```json
{
  "id": "chatcmpl-5fde5f7fffe8d6dc1f18aab4a138d4b7",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "openai/gpt-4o",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "The sky appears blue primarily due to a phenomenon called Rayleigh scattering. Here's how it works:\n\n1. **Sunlight Composition**: Sunlight, or white light, is composed of many colors, each with different wavelengths. These colors can be seen in a rainbow or through a prism.\n\n2. **Atmospheric Interaction**: As sunlight reaches the Earth's atmosphere, it collides with molecules of gases and small particles.\n\n3. **Scattering and Wavelengths**: Different colors of light are"
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 13,
    "completion_tokens": 100,
    "total_tokens": 113,
    "prompt_characters": 20,
    "response_characters": 474,
    "cost": 0.001878,
    "latency_ms": 2727
  },
  "system_fingerprint": "fp_f4d98523ab4ae852"
}
```

This structure provides the generated message, completion details, and detailed usage metrics for each request.

## Detailed Explanation of Parameters

### Required Parameters

- **messages** (array): A sequence of message objects in the conversation. Each message has:
  - **role** (string): The role of the message in the conversation. Possible values: `system`, `user`, `assistant`.
  - **content** (string): The content of the message.

### Message Roles

- **system**: This message type is used to guide the AI's behavior throughout the conversation. It sets the rules or parameters for how the AI should respond. For example, the system message might instruct the AI to speak in a specific language, adopt a particular tone, or adhere to certain boundaries in its replies. It's useful for defining the scope and role of the assistant, ensuring it stays within the desired context.
  
  **Example use case**: Defining the AI's behavior.
  
  ```json
  {
    "role": "system",
    "content": "You are a helpful assistant that speaks only in Swedish."
  }
  ```

- **user**: The user message represents the actual input or query from the person interacting with the AI. It's the prompt or question the user is submitting to the AI, and this message is crucial as it dictates what the AI will respond to. The content here is typically dynamic based on what the user is asking or requesting at any given moment.

  **Example use case**: The user's request to the AI.
  
  ```json
  {
    "role": "user",
    "content": "Why is the sky blue?"
  }
  ```

- **assistant**: This message type is the AI's response or any generated information that contributes to the conversation. It can be used for knowledge retrieval (such as in Retrieval-Augmented Generation, RAG) or historical memory when responding to ongoing conversations. The assistant message can be stored and used in context to improve the model’s ability to respond appropriately over a series of interactions.

  **Example use case**: AI's response or retrieved information.
  
  ```json
  {
    "role": "assistant",
    "content": "The sky is blue because of a phenomenon called Rayleigh scattering..."
  }
  ```

- **model** (string): Specifies the AI model to use. Normally a single base model name, you can provide up to 5 comma-separated models for multi-model queries which leverages our super query capabilities (Note: Some other features may not work with Super Query, such as pools for example)

### Optional Parameters

- **provider** (string): Optionally, specify the AI provider, or omit this field to let the system choose the best-performing one.
  
- **rag_tune** (string): Use this to specify a RAG tune or vector collection for augmenting language model queries with data from a specified vector database.

- **routing** (string): Defines how the call should be routed when multiple providers exist for a model. Options are:
  - `price`: Chooses the cheapest provider.
  - `perf`: Selects based on lowest latency for prompt size.
  - `perf_avg`: Chooses based on average latency.

### Generation Control Parameters (Grouped)

You can fine-tune the model's output by controlling randomness, creativity, and repetition through the following parameters:

- **temperature** (number): Controls randomness in the output. A lower value makes the model more deterministic, while a higher value increases randomness.
- **top_p** (number): Cumulative probability cutoff for token selection. A lower value keeps the output more deterministic, while a higher value increases creativity.
- **top_k** (integer): Limits the token selection to the top-k most likely tokens. A lower value makes the response more predictable.
- **frequency_penalty** (number): Penalizes tokens based on their frequency in the output, promoting diversity.
- **presence_penalty** (number): Penalizes tokens that have already appeared, encouraging new content.

Here’s a sample API call with these options:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "messages": [
    {
      "role": "user",
      "content": "Tell me a story about a talking cat."
    }
  ],
  "temperature": 0.7,
  "top_p": 0.9,
  "top_k": 50,
  "frequency_penalty": 0.2,
  "presence_penalty": 0.5
}'
```

### Beam Search Parameters
 Note: This is not available on all models, if the model you support does not support it, the parameter will be dropped.

- **beam_size** (integer): Determines the number of beams (sequences) to keep at each step during generation. This setting increases the probability of finding optimal sequences but requires more computational resources.

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "llama-3.2-1b-instruct",
  "messages": [
    {
      "role": "user",
      "content": "What is the capital of France?"
    }
  ],
  "beam_size": 5
}'
```

### Other Parameters

- **n** (integer): Number of completions to generate for a single input.
- **max_tokens** (integer): The maximum number of tokens to generate for each completion.
- **stream** (boolean): If true, the API returns a stream of data chunks as the completion is generated, rather than waiting for the entire response.

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "messages": [
    {
      "role": "user",
      "content": "How does streaming work in AI?"
    }
  ],
  "stream": true
}'
```

### Integrity and Verification

- **integrity** (integer): This setting controls the verification process, where the model can vote on its own response to enhance accuracy and reduce hallucinations. Set this to 12 or 13.
- **integrity_model** (string): Choose a model for integrity checks (optional).

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "gpt-4o",
  "messages": [
    {
      "role": "user",
      "content": "Why is the sky blue?"
    }
  ],
  "integrity": 13,
  "integrity_model": "gpt-3.5-turbo"
}'
```

### Example of Streaming Response

```json
data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":0,"delta":{"role":"assistant","content":""},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":1,"delta":{"content":"The"},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}
...
data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":100,"delta":{"content":" sky"},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":101,"delta":{"content":""},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":102,"delta":{"content":""},"logprobs":null,"finish_reason":null}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"provider":"openrouter","model":"openai/gpt-4o","choices":[{"index":0,"delta":{"content":""},"logprobs":null,"finish_reason":"stop"}],"system_fingerprint":"null"}

data: {"id":"chatcmpl-fc2e9121675cd68b07b6d1eb5e2b11e8","object":"chat.completion.chunk","created":1729535567,"model":"openai/gpt-4o","system_fingerprint":"null","choices":[],"usage":{"prompt_tokens":13,"completion_tokens":100,"total_tokens":113,"prompt_characters":20,"response_characters":527,"cost":0.001878,"latency_ms":2831}}

data: [DONE]
```

---

## Usage Metrics in the Response

We provide comprehensive usage data with every request to help you track costs and performance. Metrics include:

- **prompt_tokens**: Number of tokens in the input prompt.
- **completion_tokens**: Number of tokens generated in the model’s response.
- **total_tokens**: Sum of `prompt_tokens` and `completion_tokens`.
- **prompt_characters**: Number of characters in the input prompt.
- **response_characters**: Number of characters in the model’s response.
- **cost**: The estimated cost of the request.
- **latency_ms**: Time taken for the model to generate a response.

### Example Response with Usage Metrics

```json
{
  "id": "chatcmpl-5fde5f7fffe8d6dc1f18aab4a138d4b7",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "openai/gpt-4o",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "The sky appears blue primarily due to a phenomenon called Rayleigh scattering. Here's how it works..."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 13,
    "completion_tokens": 100,
    "total_tokens": 113,
    "prompt_characters": 20,
    "response_characters": 474,
    "cost": 0.001878,
    "latency_ms": 2727
  },
  "system_fingerprint": "fp_f4d98523ab4ae852"
}
```

**Note:** We are a leader in query usage reporting, offering extensive data tracking for every request. Additionally, historical billing data is available via API for audit purposes.
