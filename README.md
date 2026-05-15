# AI Meeting Notes & Action Item Automation

An AI-powered meeting automation workflow built using **n8n**, **Groq Llama 3.1**, **Gmail**, and **Google Sheets**.

The system automatically summarizes meetings, extracts action items, assigns owners and priorities, stores tasks, sends recap emails, and tracks reminders — all in one workflow.

---

# Overview

Meeting discussions often end with action items getting forgotten, deadlines being missed, and no structured follow-up process.

This workflow solves that problem by using AI to automatically:

- summarize meetings
- extract action items
- identify owners
- assign priorities
- detect deadlines
- store tasks
- send meeting recap emails
- send reminder emails for pending tasks
- update reminder status automatically

---

# Features

✅ AI meeting summarization  
✅ Automatic action item extraction  
✅ Owner assignment  
✅ Priority classification  
✅ Deadline detection  
✅ Google Sheets task tracking  
✅ Gmail meeting recap emails  
✅ Pending task reminders  
✅ Reminder status tracking  
✅ Structured JSON parsing  
✅ End-to-end workflow automation  

---

# Workflow Architecture

```text
Meeting Input
    ↓
Meeting Transcript
    ↓
Generate Summary & Action Items (Groq Llama 3.1)
    ↓
Parse Meeting Insights
    ├── Send Meeting Recap Email
    │
    └── Extract Action Items
             ↓
        Store Tasks Tracker (Google Sheets)
             ↓
        Check Pending Action Items
             ↓
        Send Owner Reminder
             ↓
        Mark Reminder Sent
```

---

# Full Workflow Screenshot

## Workflow Overview

![Workflow Overview](screenshots/meeting-action-items-workflow.png)

---

# Technologies Used

| Tool | Purpose |
|------|----------|
| n8n | Workflow automation |
| Groq API | LLM inference |
| Llama 3.1 8B Instant | Meeting analysis |
| Gmail API | Recap & reminder emails |
| Google Sheets API | Task storage & tracking |
| JavaScript | Parsing and automation logic |

---

# AI Processing

The AI model analyzes meeting transcripts and generates:

- Meeting summary
- Action items
- Task owners
- Priorities
- Deadlines

Example AI output:

```json
{
  "summary": "Discussion about scaling millet powder business",
  "tasks": [
    {
      "task": "Create a proper website",
      "owner": "Jagadeesh",
      "deadline": "TBD",
      "priority": "High"
    }
  ]
}
```

---

# Google Sheets Output

Tasks are stored automatically with:

| Column | Purpose |
|---------|----------|
| Task | Extracted action item |
| Owner | Responsible person |
| Deadline | Due date |
| Priority | High / Medium / Low |
| Status | Pending / Completed |
| Reminder Sent | Tracks reminder emails |
| Created At | Timestamp |

Example:

| Task | Owner | Status | Reminder Sent |
|------|------|------|------|
| Create website | Jagadeesh | Pending | yes |

---

# Email Outputs

## 1. Meeting Recap Email

Includes:

- Meeting summary
- Action items
- Owners
- Deadlines
- Priorities

---

## 2. Owner Reminder Email

Automatically sent for:

```text
Status = Pending
```

Reminder example:

```text
Reminder: Pending Meeting Action Item

Task:
Create website

Owner:
Jagadeesh

Priority:
High
```

---

# Example Use Cases

- Client meetings
- Team standups
- Project discussions
- Operations meetings
- Sales calls
- Startup planning
- Internal reviews

---

# Project Structure

```text
.
├── meeting_action_items_workflow.json
├── README.md
├── .gitignore
└── screenshots/
      └── meeting-action-items-workflow.png
```

---

# Setup Instructions

## 1. Clone repository

```bash
git clone https://github.com/your-username/repository-name.git
cd repository-name
```

---

## 2. Import workflow

Open n8n:

```text
Workflows
↓
Import
↓
Select JSON workflow
```

---

## 3. Configure credentials

Connect:

- Groq API
- Gmail OAuth
- Google Sheets OAuth

---

## 4. Create Google Sheet

Columns required:

```text
Task
Owner
Deadline
Priority
Status
Reminder Sent
Created At
```

---

## 5. Replace placeholders

Update:

```text
{{YOUR_EMAIL}}
{{GOOGLE_SHEETS}}
{{GROQ_CREDENTIAL}}
```

---

## 6. Execute workflow

Run:

```text
Meeting Input
↓
Workflow Execution
```

---

# Security Notes

Never commit:

- Real Gmail credentials
- Groq API keys
- Google Sheets OAuth IDs
- Personal email addresses

Use placeholders in public repositories.

---

# Future Improvements

- Zoom transcript integration
- Google Meet integration
- Slack / Telegram reminders
- Dashboard analytics
- Multi-user support
- Calendar sync
- Whisper transcription
- CRM integration

---

# Problem Solved

**Problem:**

People leave meetings, but action items disappear.

**Solution:**

Meeting notes → AI summary → task extraction → owner assignment → reminders → tracking

---

# Author

**Jagadeesh S**

Built using n8n + Groq + Gmail + Google Sheets
