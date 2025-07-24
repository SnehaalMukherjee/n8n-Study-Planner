# 📚 Smart Semester Planner using n8n + Gemini

This project is a **personalized academic planning system** built with [n8n](https://n8n.io), designed to help students streamline their semester with custom study roadmaps. It uses **Google Gemini API** to generate roadmap content, then sends it via **Gmail** and syncs all tasks with **Google Calendar** — all done automatically.

---

## 🚀 What It Does

- 🧠 Generates a smart 6-month learning roadmap based on selected tech stacks (like AI/ML, Web Dev, etc.)
- 📨 Delivers the roadmap as a beautifully formatted HTML email
- 📅 Automatically schedules roadmap goals as calendar events
- 🔁 Transforms Gemini output into structured task schedules
- 🧩 Fully modular workflow — easy to expand and reuse in n8n

---

## 🛠️ Workflow Overview

1. Student submits form details (name, year, email, tech interest, etc.)
2. Google Gemini API returns a semester plan in HTML format
3. One code node extracts the email & HTML
4. Another code node slices tasks and assigns dates across 6 months
5. Gmail node sends the personalized roadmap
6. Calendar node inserts each task with equal distribution over the term

---

## 📦 Getting Started

### Step 1: Load the Workflow

1. Clone this repo or download the file `academic_stack_planner_email_updated.json`
2. Open your local or cloud **n8n** instance
3. Click **Workflows → Import → Upload JSON**
4. Paste or upload the downloaded workflow

### Step 2: Connect Your Credentials

You’ll need the following credentials set up in n8n:

| Tool              | Credential Type  | Permissions Needed                                     |
|------------------|------------------|--------------------------------------------------------|
| Gmail            | OAuth2           | `https://www.googleapis.com/auth/gmail.send`          |
| Google Calendar  | OAuth2           | `https://www.googleapis.com/auth/calendar`            |
| Gemini AI        | API Key          | Use from Google AI Studio                             |

---

## 🧾 Sample Input Data

This is the structure of data expected by the workflow:

```json
{
  "Enter is your name?": "Snehaal",
  "Enter is your discipline of study?": "BCA",
  "Enter year are you in?": "2",
  "Which stack would you like the roadmap to be on?": "Full Stack",
  "Enter is your current level of understanding?": "Beginner",
  "Briefly describe your current skills (only keywords)?": "HTML, CSS, Python",
  "Enter is your email id?": "snehaal@example.com"
}
