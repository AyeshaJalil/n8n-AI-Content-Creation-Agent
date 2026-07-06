# AI Content Creation & Instagram Automation Agent

An end-to-end AI-powered content automation workflow built with **n8n** that automatically generates Instagram-ready marketing content, creates AI-generated visuals, uploads them to Cloudinary, and publishes posts directly to Instagram.

This project demonstrates how Large Language Models (LLMs), AI image generation, cloud storage, and social media APIs can be orchestrated into a fully automated content marketing pipeline.

---

## Overview

Creating high-quality social media content requires multiple manual steps including writing captions, generating hashtags, designing visuals, uploading images, and publishing posts. This workflow automates the complete process using AI.

The system retrieves business information from Google Sheets, generates marketing content using an AI agent, creates an image with Hugging Face FLUX, uploads the generated image to Cloudinary, and finally publishes the post to Instagram automatically.

---

# Workflow Architecture

```
Schedule Trigger
        │
        ▼
Google Sheets
(Read Latest Form Submission)
        │
        ▼
Code Node
(Pick Latest Row)
        │
        ▼
AI Agent (OpenRouter)
        │
        ▼
Generates
• Caption
• Marketing Hooks
• Hashtags
• Image Prompt
        │
        ▼
Code Node
(Parse & Format Output)
        │
        ▼
Hugging Face FLUX.1 Schnell
(AI Image Generation)
        │
        ▼
Cloudinary
(Upload Image & Generate Public URL)
        │
        ▼
Instagram
(Create & Publish Post)
```

---

# Features

- AI-generated marketing captions
- Business-specific content generation
- AI-generated hooks for engagement
- Automatic hashtag generation
- AI-powered Instagram image generation
- Automatic image hosting using Cloudinary
- Direct Instagram publishing
- Fully automated end-to-end workflow
- Modular architecture for easy customization

---

# Tech Stack

| Technology | Purpose |
|------------|---------|
| n8n | Workflow Automation |
| Google Sheets | Business Data Source |
| OpenRouter | AI Text Generation |
| Hugging Face FLUX.1 Schnell | AI Image Generation |
| JavaScript | Data Processing |
| Cloudinary | Image Hosting |
| Instagram API | Social Media Publishing |

---

# Workflow Explanation

### 1. Schedule Trigger
The workflow starts automatically on a scheduled interval.

---

### 2. Google Sheets

Reads the latest business submission containing information such as:

- Business Name
- Niche
- Marketing Goal
- Target Audience

---

### 3. Code Node

Filters the latest submission so that only one request is processed during each workflow execution.

---

### 4. AI Agent (OpenRouter)

The AI agent generates:

- Marketing Caption
- Engagement Hooks
- Relevant Hashtags
- Detailed Image Prompt

---

### 5. Code Node

Parses and formats the AI output into a clean structure that can be consumed by the image generation API.

---

### 6. Hugging Face FLUX.1 Schnell

Uses the generated image prompt to create a unique AI-generated marketing image for the Instagram post.

---

### 7. Cloudinary

The generated image is uploaded to Cloudinary which returns a secure public image URL.

Cloudinary is required because the Instagram Graph API cannot publish images directly from binary data. Instead, it requires a publicly accessible image URL.

---

### 8. Instagram API

The workflow automatically creates and publishes the Instagram post using:

- AI-generated caption
- AI-generated image
- Generated hashtags

No manual intervention is required.

---


# Why Cloudinary?

Hugging Face generates images as binary files inside the n8n workflow.

Instagram's Graph API requires a publicly accessible image URL before a post can be published.

Cloudinary acts as an image hosting service by:

- Uploading the generated image
- Creating a secure public URL
- Returning the URL to the workflow
- Allowing Instagram to access and publish the image

---

# Future Improvements

- LinkedIn Automation
- Facebook Posting
- Threads Integration
- X (Twitter) Integration
- AI Content Calendar
- Trending Topic Detection
- Brand Template Selection
- Multi-language Content Generation
- Performance Analytics Dashboard

---

# Skills Demonstrated

- Workflow Automation
- AI Agent Development
- Prompt Engineering
- API Integration
- REST APIs
- Image Generation
- Cloud Storage Integration
- Social Media Automation
- JavaScript
- End-to-End AI Orchestration
- Business Process Automation

---

# Author

Ayesha Jalil

AI Automation Engineer

Specializing in AI-powered workflow automation, LLM integrations, API orchestration, and business process automation using n8n.
