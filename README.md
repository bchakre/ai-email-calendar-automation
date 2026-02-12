# 🚀 AI Email-to-Calendar Automation System  
### Intelligent Meeting Scheduling using n8n + Google AI + Google APIs

---

## 🧠 Overview

This project is an AI-powered meeting automation system that transforms unstructured email requests into fully scheduled Google Calendar events — automatically.

It monitors incoming Gmail messages, extracts structured meeting details using Google Generative AI, validates the extracted data, creates a Google Calendar event, and sends a professional confirmation reply — all without manual intervention.

> 📩 Email in → 📅 Calendar event out → ✉️ Auto confirmation sent

---

## 🎯 Problem Statement

Manually scheduling meetings from emails involves:

- Reading and interpreting email content  
- Extracting date and time  
- Checking calendar availability  
- Creating the event  
- Sending confirmation reply  

This process is repetitive, time-consuming, and prone to human error.

---

## 💡 Solution

This automation system eliminates manual scheduling by:

- Monitoring incoming Gmail messages  
- Using AI to extract structured meeting details  
- Validating required fields (date & time)  
- Automatically creating a Google Calendar event  
- Sending a professional confirmation reply  

---

## ⚙️ System Architecture

```
Gmail Trigger
      ↓
Edit Fields (Email Cleanup)
      ↓
HTTP Request (Google Generative AI)
      ↓
JSON Parsing (Structured Output)
      ↓
IF Validation (Date & Time Check)
      ↓
Create Google Calendar Event
      ↓
Reply to Sender
```

---

## 🛠 Tech Stack

| Component | Technology |
|------------|------------|
| Workflow Engine | n8n |
| AI Extraction | Google Generative AI API |
| Email Integration | Gmail API |
| Calendar Integration | Google Calendar API |
| Data Handling | JavaScript Expressions |
| Version Control | Git & GitHub |

---

## 🔍 AI Extraction Example

### 📩 Input Email

```
Hi,
Let’s schedule a meeting on 2026-02-15 at 14:30 for 45 minutes to discuss AI automation.
Regards
```

### 🤖 Extracted JSON Output

```json
{
  "date": "2026-02-15",
  "time": "14:30",
  "duration_minutes": 45,
  "topic": "AI automation"
}
```

---

## 📅 Dynamic Date-Time Handling

### Start Time

```javascript
{{ $json.ai_parsed.date + 'T' + $json.ai_parsed.time + ':00' }}
```

### End Time

```javascript
Start time + duration_minutes
```

### Features

- Automatic ISO datetime formatting  
- Dynamic end-time calculation  
- Default duration fallback (60 minutes if missing)  
- Safe validation using IF node  

---

## ✉️ Automated Confirmation Email

Example reply:

```
Hi,

Thank you for your message.
I am available at 14:30 on 2026-02-15.
The meeting has been scheduled successfully.

Looking forward to connecting.

Best regards,
Buddhabhushan
```

---

## 🛡 Validation Logic

The workflow includes safeguards:

- Ensures `date` is not null  
- Ensures `time` is not null  
- Prevents invalid calendar bookings  
- Avoids incomplete event creation  

---

## 🌟 Key Features

- AI-based unstructured text parsing  
- Structured JSON enforcement  
- Dynamic event creation  
- Professional auto-reply system  
- Modular & scalable workflow design  
- Fully low-code implementation  
- Production-ready conditional logic  

---

## 📈 Impact

- ⏳ Saves manual scheduling time  
- 🧠 Reduces cognitive load  
- 📅 Eliminates booking errors  
- 🤖 Demonstrates AI + Automation integration  
- 💼 Portfolio-ready real-world system  

---

## 🔮 Future Enhancements

- Smart availability checking before booking  
- Conflict detection logic  
- Automatic Google Meet link generation  
- Time zone handling improvements  
- Slack / WhatsApp integration  
- Meeting database logging  

---

## 🧑‍💻 Author

**Buddhabhushan Chakre**  
Data Scientist 
Focused on building intelligent workflow systems that combine AI with real-world productivity tools.

---

## 📌 Why This Project Matters

This project demonstrates:

- API integration skills  
- AI-driven data extraction  
- Workflow automation architecture  
- Conditional logic implementation  
- Production-safe automation design  

It bridges AI capabilities with practical business automation use cases.

---
