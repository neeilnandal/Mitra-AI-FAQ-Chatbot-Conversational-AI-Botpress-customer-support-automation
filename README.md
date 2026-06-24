# Mitra: AI FAQ Chatbot for Customer Self-Service

Mitra is a website-embedded AI FAQ chatbot built for **Nfilade Security Solutions / MyNetSec** to help customers resolve common Tier-1 support queries through self-service.

The chatbot was implemented using **Botpress Cloud Webchat** and integrated into the company website with lightweight HTML and JavaScript. It gave customers a simple conversational interface for frequently asked questions, reducing repetitive manual support workload and helping resolve approximately **50% of Tier-1 support queries** without human intervention.

## Project Snapshot

| Area                  | Details                                                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| **Status**            | Complete                                                                                                                            |
| **Problem**           | Reduce repetitive Tier-1 support workload while giving customers faster self-service access to common answers                       |
| **Approach**          | Botpress-powered FAQ assistant embedded in a customer-facing website, with guided responses and escalation for unsupported queries  |
| **Tech**              | Botpress Cloud, Botpress Webchat, HTML, JavaScript, browser session storage                                                         |
| **Reproducibility**   | Setup, deployment, test scenarios, and web-embed artefacts are documented in `docs/`, `deployment/`, and `tests/`                   |
| **Validation**        | Common Tier-1 query testing, fallback and escalation-path review, and deployment-focused frontend/security hygiene                  |
| **Observed outcome**  | Approximately 50% of Tier-1 support queries were resolved through self-service in the documented deployment context                 |
| **Key design choice** | Used a maintainable conversational platform instead of over-engineering a custom NLP stack for a narrow FAQ workflow                |
| **Scope**             | Customer-support automation prototype; outcome metrics should be interpreted within the documented query set and deployment context |


## Repository Summary

**Project type:** Conversational AI chatbot integration
**Use case:** Customer support automation
**Platform:** Botpress Cloud
**Frontend integration:** HTML, JavaScript
**Chatbot name:** Mitra
**Business outcome:** Around 50% Tier-1 support query resolution through self-service

## Problem

Customer support teams often handle the same basic questions repeatedly. These questions are usually important, but they do not always require manual support.

Typical examples include:

* How do I contact support?
* How do I access my account?
* Where can I find service information?
* How do I raise a support request?
* What should I do if I face a login issue?

Before Mitra, customers depended more heavily on static FAQ pages or manual support channels. This created unnecessary waiting time for users and repetitive work for the support team.

## First-Principles View

The real problem was not “build a chatbot.”

The real problem was:

> Customers needed quick answers to repeated support questions, and the support team needed fewer low-complexity tickets.

A full custom NLP system would have been excessive for this scope. A faster and more maintainable solution was to use a conversational AI platform, configure the support flow, and embed it directly into the customer-facing website.

That is why Botpress was a practical fit.

## Solution

Mitra was built as a Botpress-powered FAQ assistant and embedded into the company website using the Botpress Webchat script.

The chatbot acts as a first-response support layer. Users can ask questions in natural language, receive guided responses, and resolve common issues without submitting a ticket.

For unclear or unsupported questions, the chatbot can guide the user toward human support or the appropriate escalation path.

## Key Features

* Website-embedded chatbot interface
* Branded assistant named **Mitra**
* Conversational FAQ support
* Customer self-service for common Tier-1 queries
* Botpress Cloud Webchat integration
* Session-based chat experience
* Lightweight HTML and JavaScript deployment
* Scalable first-response layer for support automation

## Tech Stack

| Area               | Technology                                   |
| ------------------ | -------------------------------------------- |
| Chatbot Platform   | Botpress Cloud                               |
| Webchat Embed      | Botpress Webchat                             |
| Frontend           | HTML, JavaScript                             |
| UI Theme           | Prism                                        |
| Session Handling   | Browser session storage                      |
| Deployment Context | Website-based customer support               |
| Use Case           | FAQ automation and Tier-1 support deflection |

## System Flow

```text
Customer visits website
        |
Botpress Webchat loads
        |
Customer asks a support question
        |
Mitra matches the query to a relevant FAQ or support flow
        |
Chatbot returns a structured response
        |
Customer resolves the issue or escalates to human support
```

## Webchat Integration

The chatbot was embedded using Botpress Cloud’s webchat script and configuration file.

```html
<script src="https://cdn.botpress.cloud/webchat/v1/inject.js"></script>
<script src="https://mediafiles.botpress.cloud/b53b849f-1eb2-493a-9746-fc818d576c5c/webchat/config.js" defer></script>
```

A simplified initialization example is shown below:

```html
<script>
  window.botpressWebChat.init({
    composerPlaceholder: "Chat with Mitra",
    botConversationDescription: "Customer support chatbot for FAQ self-service",
    botName: "Mitra",
    themeName: "prism",
    themeColor: "#2563eb",
    useSessionStorage: true,
    showBotInfoPage: true
  });
</script>
```

## Clean HTML Embed Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Mitra FAQ Chatbot</title>
  <meta
    name="description"
    content="Mitra is a Botpress-powered AI FAQ chatbot built for customer self-service and Tier-1 support automation."
  />

  <script src="https://cdn.botpress.cloud/webchat/v1/inject.js"></script>
  <script
    src="https://mediafiles.botpress.cloud/b53b849f-1eb2-493a-9746-fc818d576c5c/webchat/config.js"
    defer>
  </script>
</head>

<body>
  <script>
    window.addEventListener("load", function () {
      window.botpressWebChat.init({
        composerPlaceholder: "Chat with Mitra",
        botConversationDescription: "Customer support chatbot for FAQ self-service",
        botId: "b53b849f-1eb2-493a-9746-fc818d576c5c",
        hostUrl: "https://cdn.botpress.cloud/webchat/v1",
        messagingUrl: "https://messaging.botpress.cloud",
        clientId: "b53b849f-1eb2-493a-9746-fc818d576c5c",
        webhookId: "0bb8fa12-c2b5-4dd9-923f-4fd1679c208b",
        lazySocket: true,
        themeName: "prism",
        botName: "Mitra",
        frontendVersion: "v1",
        useSessionStorage: true,
        showBotInfoPage: true,
        showPoweredBy: true,
        theme: "prism",
        themeColor: "#2563eb",
        allowedOrigins: []
      });
    });
  </script>
</body>
</html>
```

## Measuring Impact

The chatbot’s value was measured through support deflection.

Primary success metric:

```text
Tier-1 self-service resolution rate = resolved chatbot queries / total Tier-1 support queries
```

Observed result:

```text
Approximately 50% of Tier-1 support queries were resolved through self-service
```

This means the chatbot helped reduce repetitive support workload while giving customers faster access to basic help.

## My Contribution

My contribution included:

* Configuring the Botpress chatbot experience
* Embedding the chatbot into the customer-facing web interface
* Customizing the assistant identity as **Mitra**
* Setting up webchat behavior and session handling
* Aligning chatbot responses with FAQ and support needs
* Testing the assistant against common Tier-1 customer queries
* Improving the web embed structure for cleaner deployment
* Reviewing the implementation for basic frontend and security hygiene

## Decision Logic

The project was designed around a practical build-vs-buy decision.

| Option                                | Pros                                                    | Cons                                                         | Decision     |
| ------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------ | ------------ |
| Build custom NLP chatbot from scratch | Full control, deeper ML ownership                       | Slower, harder to maintain, unnecessary for narrow FAQ scope | Not selected |
| Use static FAQ page only              | Simple, low cost                                        | Poor user experience, no conversational flow                 | Not enough   |
| Use Botpress webchat                  | Fast deployment, maintainable, conversational interface | Platform dependency                                          | Selected     |

Botpress was the right choice because the business needed fast support automation, not research-grade NLP.

## OODA Summary

### Observe

Customers were asking repeated Tier-1 support questions. Support teams were spending time on issues that could be answered through existing FAQ knowledge.

### Orient

The problem was narrow, repetitive, and support-focused. A low-code chatbot platform was more suitable than building a custom NLP model from scratch.

### Decide

Use Botpress Cloud Webchat to deploy a branded FAQ assistant directly on the website.

### Act

Configure the chatbot, embed it into the web page, test common support queries, and use the assistant as a first-response customer support layer.

## SEO Keywords

Relevant keywords for this project:

* AI FAQ chatbot
* Botpress chatbot
* customer self-service chatbot
* Tier-1 support automation
* conversational AI
* support deflection
* website chatbot
* customer support automation
* AI helpdesk assistant
* FAQ automation

## Future Improvements

Potential next steps include:

* Add analytics for unanswered questions
* Connect chatbot logs to support dashboards
* Add human handoff for unresolved queries
* Integrate with CRM or ticketing tools
* Add multilingual support
* Improve FAQ coverage using conversation data
* Add semantic search or retrieval-augmented generation for richer answers
* Create an admin workflow for updating FAQ content
