---
title: Preferred Routing Guide
sidebar_label: Preffered Routing
tags:
  - Routing
  - AI Performance
  - AI Cost Efficiency
keywords:
  - Routing
  - AI Performance
  - AI Pricing
  - OpenAI Integration
  - AI Business Solutions
  - GPT-4o
  - OpenAI
  - Routing Options
  - Preferred Routing API
  - AI Request Routing
  - API Provider Selection
  - Cost-based Routing API
  - Performance-based Routing API
  - AI API Routing Options
  - API Routing Parameters
  - API Routing Strategies
  - AI Performance Optimization
  - AI Cost Optimization
  - AI Provider Management
  - API Routing Configuration
  - API Route Selection
  - AI Response Speed
  - AI Cost Efficiency
  - AI Request Management
  - AI Routing Features
  - API Multiple Providers
  - API Routing Guide
  - API Routing Documentation
  - API Routing Best Practices
  - API Routing Setup
  - API Routing Benefits
  - AI Workflow Optimization
  - AI Operational Goals
  - API Routing Flexibility
  - API Routing Customization
  - AI Deployment Routing
  - API Request Routing
  - AI Routing Solutions
  - API Routing Integration
  - AI Routing Control
  - API Routing Cost Efficiency
  - API Routing Performance
  - AI Routing Techniques
  - API Routing Functionality
  - AI Routing Options
  - API Routing Overview
  - AI Routing Configuration
  - API Routing Management
  - AI Routing Benefits
  - API Routing Use Cases
  - AI Routing Examples
  - API Routing Parameters
  - AI Routing Strategies
  - API Routing Preferences
  - AI Routing Customization
  - API Routing Features
  - AI Routing Setup
  - API Routing Steps
  - AI Routing Guide
sidebar_position: 10
---

::div{align="center"}
![Preferred Routing Feature Banner](/docs/img/Features/routing-banner.png){width="100%"}
::

Discover the flexibility of our Preferred Routing feature, designed to give users control over how their AI requests are handled when multiple providers are available for a selected model. With this feature, users can specify routing based on price or performance, ensuring that their needs are always met, whether focused on cost efficiency or response speed.

## Why Use Preferred Routing?

Preferred Routing offers a highly customizable approach to handling AI requests by allowing users to choose between the most cost-effective or the fastest provider. This is particularly useful for businesses that either want to minimize operational costs or prioritize performance for critical use cases.

## Understanding Preferred Routing Options

### Routing Types

- **Price**: Automatically routes your request to the least expensive provider available for the selected model. Ideal for use cases where saving money is more important than response time.
- **Perf**: (Default) Routes your request to the most responsive provider based on your prompt size, ensuring the fastest possible response.
- **Perf-Avg**: Selects the provider with the best average latency across all prompt sizes, ensuring consistent response times in various scenarios.

## How to Use Preferred Routing

Using Preferred Routing in your AI workflows is simple. Here's a typical API call with the routing parameter:

```bash
curl -L -X POST 'https://apipie.ai/v1/chat/completions' \
-H 'Content-Type: application/json' \
-H 'Accept: application/json' \
-H 'Authorization: Bearer <TOKEN>' \
--data-raw '{
  "messages": [
    {
      "role": "system",
      "content": "why is the sky blue?"
    }
  ],
  "model": "gpt-3.5-turbo",
  "routing": "perf", //route to the most responsive provider of this model
  "temperature": 1,
}'
```

This example demonstrates how to use the `routing` parameter in an API request. By default, the `routing` option is set to `perf`, but users can modify it to either `price` or `perf-avg` based on their needs.

## Benefits of Preferred Routing for Businesses

By offering both price-based and performance-based routing, Preferred Routing allows businesses to customize their AI deployments to meet different operational goals:

- **Cost Reduction**: Use price routing to minimize expenses for routine tasks where speed is not critical.
- **Optimal Performance**: Leverage performance routing to ensure fast response times for time-sensitive tasks.

## Setting Up Preferred Routing

To start using Preferred Routing effectively, follow these steps:

1. **Configure Your API Call:*** Add the `routing` parameter and set it to either `price`, `perf`, or `perf-avg` depending on your needs.
2. **Monitor Costs and Latency:*** Track your usage and adjust routing settings to balance cost savings and performance as needed.

## FAQs

1. **What is the default routing option?*** The default routing option is `perf`, which selects the most responsive provider based on your prompt size.
2. **How does price routing work?*** Price routing selects the cheapest provider for your request, based on real-time pricing for the model.
3. **Can routing impact response time?*** Yes, selecting price routing may result in slower response times, while performance routing will optimize for speed.
4. **Can I change the routing option after sending a request?*** No, the routing option must be set when making the API call.
5. **Is Preferred Routing available for all models?*** Preferred Routing is supported for models with multiple providers. If only one provider is available, routing options are not applicable.

## Links

- [Chat Completions API](https://apipie.ai/docs/api/chatcompletions)
- [Fetch Models API](https://apipie.ai/docs/api/fetchmodels)

## Conclusion

Preferred Routing offers users the flexibility to prioritize either cost savings or performance when making AI requests. Whether your focus is on efficiency or speed, this feature ensures that your needs are met seamlessly across multiple providers.
