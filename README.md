# OverView
![](Annotation%202025-12-16%20120051.jpg)
--
![](Annotation%202025-12-16%20120019.jpg)


# AutoContentFlow

AutoContentFlow is a fully automated workflow for generating, preparing, and publishing technical content to LinkedIn using Google Gemini, Google Sheets, and n8n. It’s designed for developers, engineers, and content creators who want to streamline their content pipeline with AI.

## 🚀 Features

- **Scheduled Idea Generation**  
  Uses Gemini Chat and Gemini Research to generate high-value post ideas based on past content.

- **Structured Output Parsing**  
  Ensures clean JSON output with fields like name, idea, title, text, and image description.

- **Google Sheets Integration**  
  Reads past ideas and saves new ones with status tracking.

- **Automated Publishing**  
  Picks ready posts, downloads images, processes them, and publishes to LinkedIn.

- **Status Update**  
  Automatically updates post status after publishing.

## 🧠 Gemini Research Tool

A sub-workflow that performs web research using Gemini API to enrich post ideas with concrete facts and examples.

## 🧩 Workflow Breakdown

### 1. Idea Generation
- Triggered daily at 5 AM
- Reads past ideas from Google Sheets
- Joins ideas into a single prompt
- Generates new post using Gemini Chat + Gemini Research
- Parses output and saves to Sheets

### 2. Post Publishing
- Triggered daily at 4 PM
- Reads posts marked as "ready"
- Picks one, downloads its image
- Converts Google Drive link to direct download
- Sends image via HTTP request
- Publishes post to LinkedIn
- Updates status to "posted"

## 🛠 Requirements

- n8n installed and running
- Google Sheets and Drive access
- LinkedIn API credentials
- Gemini API access

## ⚠️ Security

All credentials have been removed from the shared JSON files. Make sure to reconfigure your own credentials before running.

## 📁 Files

- `Linkedin Automation.json`: Main workflow for idea generation and publishing
- `Gemini Research.json`: Sub-workflow for web research via Gemini


