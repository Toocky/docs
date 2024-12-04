---
title: Qwen Series Language Models Overview
sidebar_label: Qwen
tags:
  - Qwen
  - APIpie Integration
  - Chat Models
keywords:
  - Qwen Series
  - Qwen AI models
  - Qwen language models
  - Transformer-based NLP models
  - Instruction-based AI models
  - Chat-based AI models
  - Vision-language models
  - Large language models (LLMs)
  - AI model comparison
  - NLP applications
  - Conversational AI models
  - Qwen token capacity
  - Qwen model architecture
  - Instruction fine-tuned models
  - Vision-language AI
  - AI-powered chat solutions
  - Extended context AI models
  - API integrations for AI
  - OpenRouter Qwen models
  - EdenAI Qwen models
  - Bedrock Qwen models
  - Together platform AI
  - Qwen API examples
  - Qwen model usage
  - Qwen chat completions API
  - NLP API examples
  - AI models for chatbots
  - Instruction-based task automation
  - Multimodal AI tasks
  - Long-sequence text processing
  - Qwen model subtypes
  - Model token response capacity
  - AI for customer support
  - AI for education
  - AI for natural language understanding
  - AI in vision-language tasks
  - Enterprise AI solutions
  - AI for developers
  - Instruction-following AI models
  - AI model licensing
  - Qwen model ethical considerations
  - Safe AI deployment
  - Bias in AI models
  - Ethical AI practices
  - Qwen API
  - Qwen AI API
  - Qwen APIpie
sidebar_position: 3
---

::div{align="center"}
![Qwen Series Language Models Overview](/docs/img/Models/Qwen.jpeg){width="100%"}
::

### **Description**

The Qwen Series represents a comprehensive family of transformer-based models optimized for a wide range of NLP applications. These models leverage cutting-edge technology to deliver exceptional performance in conversational AI, instruction-following tasks, and extended-context interactions.

#### **Key Features**

- **Extended Token Capacity:** All models support up to 32,768 tokens for efficient handling of long-text inputs and context-rich conversations.
- **Multi-Provider Availability:** Accessible across platforms like OpenRouter, EdenAI, Together, and Bedrock.
- **Diverse Subtypes:** Includes Chat, Instruction, and Vision-Language variants tailored for specific applications.
- **Scalability:** Models ranging from lightweight solutions to high-capacity configurations for advanced tasks.

---

### \*\* Model List in the Qwen Series\*\*

#### \*\* Model List updates dynamically please see API Route for current list\*\*

| **Model Name**         | **Max Tokens** | **Response Tokens** | **Providers**                         | **Subtype**     |
| ---------------------- | -------------- | ------------------- | ------------------------------------- | --------------- |
| qwen-2-72b-instruct    | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| qwen-2-7b-instruct     | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-1.5B-Instruct    | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-7B-Instruct      | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen1.5-14B-Chat       | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-1.8B-Chat      | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-32B-Chat       | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-7B-Chat        | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-0.5B-Chat      | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-4B-Chat        | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| qwen-2-vl-7b-instruct  | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Vision-Language |
| qwen-2-vl-72b-instruct | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Vision-Language |
| qwen-2.5-72b-instruct  | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| qwen-2.5-7b-instruct   | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| eva-qwen-2.5-32b       | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-72B-Instruct     | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Instruction     |
| Qwen2-72B              | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-0.5B           | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-1.8B           | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-4B             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-7B             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-72B            | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen2-7B               | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen2-1.5B             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-32B            | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| Qwen1.5-14B            | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| qwen1-5\_32k           | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |
| qwen2\_32k             | 32,768         | 32,768              | OpenRouter, EdenAI, Together, Bedrock | Chat            |

---

### Example API Call

Below is an example of how to use the Chat Completions API to interact with a model from the **Qwen Series**, such as `qwen-2-7b-instruct`:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <YOUR_API_KEY>' \
--data-raw '{
  "provider": "openrouter",
  "model": "qwen-2-7b-instruct",
  "max_tokens": 150,
  "messages": [
    {
      "role": "user",
      "content": "Can you explain how photosynthesis works?"
    }
  ]
}'
```

---

### Response Example

The expected response structure for the Qwen model might look like this:

```json
{
  "id": "chatcmpl-12345example12345",
  "object": "chat.completion",
  "created": 1729535643,
  "provider": "openrouter",
  "model": "qwen-2-7b-instruct",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "content": "Photosynthesis is the process by which green plants, algae, and some bacteria convert light energy into chemical energy. Here’s how it works:\n\n1. **Light Absorption**: Plants capture light energy using a pigment called chlorophyll, which is found in chloroplasts.\n\n2. **Water and Carbon Dioxide**: They absorb water through their roots and carbon dioxide from the air.\n\n3. **Glucose Production**: The light energy is used to convert water and carbon dioxide into glucose (a sugar) and oxygen. The equation is:\n   \n   6CO2 + 6H2O + light energy → C6H12O6 + 6O2\n\nThis process provides energy for the plant and releases oxygen into the atmosphere."
      },
      "logprobs": null,
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 15,
    "completion_tokens": 125,
    "total_tokens": 140,
    "prompt_characters": 45,
    "response_characters": 520,
    "cost": 0.002250,
    "latency_ms": 3100
  },
  "system_fingerprint": "fp_123abc456def"
}
```

---

### API Highlights

- **Provider:** Specify the provider or leave blank for automatic selection.
- **Model:** Use any model from the Qwen Series, such as `qwen-2-7b-instruct` or others suited to your task.
- **Max Tokens:** Set the maximum response token count (e.g., 150 in this example).
- **Messages:** Format your request with a sequence of messages, including user input and system instructions.

This example demonstrates how to seamlessly query models from the Qwen Series for conversational or instructional tasks.

---

### **Applications**

- **Conversational AI:** Powering chatbots, virtual assistants, and other dialogue-based systems.
- **Instructional Scenarios:** Tailored for executing complex, multi-step tasks based on user inputs.
- **Vision-Language Models:** Addressing multimodal tasks combining textual and visual inputs.
- **Extended Context Tasks:** Providing coherent responses for long-sequence inputs.

---

### **Ethical Considerations**

The Qwen models are highly capable but lack inherent moderation systems. Users are encouraged to implement safeguards for appropriate deployment in sensitive contexts.

---

### **Licensing**

The Qwen Series is released under flexible licensing terms, allowing for both commercial and non-commercial usage. For detailed terms, consult the respective hosting providers.

Explore the Qwen Series on APIpie.ai today.
