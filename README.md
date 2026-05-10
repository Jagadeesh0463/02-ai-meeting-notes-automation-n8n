# AI Meeting Notes & Action Item Automation

An AI-powered workflow that automatically summarizes meetings, extracts action items, assigns owners and priorities, stores tasks in Google Sheets, and sends recap emails.

Built using n8n, Groq Llama 3.1, Gmail, and Google Sheets.

---

# Overview

Managing meeting notes manually is time-consuming and often causes important action items to get lost.

This workflow automates the entire process by using AI to:

* summarize discussions
* extract actionable tasks
* identify task owners
* assign priorities
* track deadlines
* store tasks automatically
* send clean meeting recap emails

---

# Features

* AI meeting summarization
* Automatic action item extraction
* Owner assignment
* Priority classification
* Deadline detection
* Google Sheets task tracking
* Automated Gmail recap emails
* Structured JSON parsing
* Professional workflow automation

---

# Workflow Architecture

```text
Manual Trigger
    ↓
Meeting Transcript Input
    ↓
AI Agent (Groq Llama 3.1)
    ↓
Parse AI Output
    ├── Convert Tasks to Items → Save to Google Sheets
    └── Send Meeting Recap Email
```

---

# Technologies Used

* n8n
* Groq API
* Llama 3.1 8B Instant
* Google Sheets API
* Gmail API
* JavaScript

---

# AI Processing

The AI model analyzes meeting transcripts and generates:

* meeting summaries
* action items
* task owners
* priorities
* deadlines

The workflow converts AI responses into structured JSON for reliable automation.

---

# Google Sheets Output

Tasks are automatically stored with:

* Task
* Owner
* Deadline
* Priority
* Status
* Created Timestamp

This creates a lightweight AI-powered task management system.

---

# Gmail Recap Output

After processing the meeting transcript, the workflow sends a formatted recap email containing:

* meeting summary
* extracted action items
* deadlines
* priorities
* owners

---

# Example Use Cases

* Client meetings
* Team standups
* Project discussions
* Sales calls
* Operations meetings
* Internal planning sessions

---

# Setup Instructions

1. Import workflow JSON into n8n
2. Configure Groq API credentials
3. Configure Gmail OAuth
4. Configure Google Sheets OAuth
5. Update Google Sheet columns:

   * Task
   * Owner
   * Deadline
   * Priority
   * Status
   * Created At
6. Execute workflow

---

# Future Improvements

* Zoom transcript integration
* Google Meet integration
* Telegram/Slack alerts
* Deadline reminders
* Dashboard analytics
* Multi-user support
* Whisper AI transcription

---

# Screenshots

## Workflow

screenshots/meeting-automation-workflow.png

---

# Author

Jagadeesh S
