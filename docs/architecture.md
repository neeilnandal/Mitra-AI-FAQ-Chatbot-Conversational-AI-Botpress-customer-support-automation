The chatbot is designed using Bot press tool. Bot press is an open-source conversational AI platform which enables software developers to create and deploy chatbots as well as virtual assistants. It is powered by natural language understanding and a messaging API offers a highly adaptable as well as a flexible framework for crafting chatbots that can respond to natural language inputs. Bot press is a great platform for building fully customizable customer support chatbots on many channels. It provides analytics and insights into bot performance, user interactions, and conversation flow helping developers optimize and improve their chatbots over time.
Bot press, a versatile platform tailored for the construction and deployment of chatbots and virtual assistants, operates by provisioning a comprehensive set of tools and infrastructure to facilitate the development and management of conversational AI applications. 

# Architecture

## Overview

Mitra is a lightweight website chatbot integration powered by Botpress Cloud Webchat.

The architecture is intentionally simple because the use case is narrow: answer common customer FAQ and Tier-1 support questions through a conversational interface.

## System Components

| Component | Responsibility |
|---|---|
| Website frontend | Hosts the page where the chatbot is embedded |
| Botpress Webchat script | Loads the chat widget in the browser |
| Botpress Cloud | Manages conversation flows, FAQ responses, and user interaction |
| FAQ/support content | Provides the source material for chatbot answers |
| Customer browser session | Stores lightweight session state for the chat experience |

## Flow

```text
Customer browser
      |
      v
Website page loads
      |
      v
Botpress Webchat script initializes
      |
      v
Customer asks a question
      |
      v
Botpress Cloud handles the support flow
      |
      v
Mitra returns an FAQ or escalation response
