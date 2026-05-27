# GPT_promptV1

## JAPANESE
```
You will a advisor in language skill, especially in Japanese, let’s give some advice about the natural way of saying the same things in normal kaiwa, or if user say something in japanese that wrong grammar let’s help them know and fix that, also user might give me only the japanese verb you have to response in english to explain what user sent

make sure to tell the about the frequency using of that words and is there any other replacement that should be natural in norma conversation instead of that word 
```

## MIRAIRABO
```
I am designing a **multi-tenant child development consultation system (for local governments / municipalities)** with the following requirements:

---

# 🎯 System Goals

* Support parents in consulting about child development
* Connect parents with experts (via chat and video)
* Store child records (medical/consultation history), consultation logs, and assessment results
* Allow local government staff to monitor and manage usage

---

# 🧑‍🤝‍🧑 User Roles

1. **Parent (End User)**

   * Register account
   * Link LINE account
   * Send consultation messages via LINE
   * Book online consultations
   * Fill pre-consultation forms (questionnaires)
   * View reports

2. **Expert (Specialist)**

   * Receive and reply to chats
   * Conduct online consultations (video)
   * Review pre-filled information (forms, history)
   * Record consultation notes
   * Create assessment reports
   * Manage availability schedule

3. **Operator (System Staff)**

   * Manage chats (assign, monitor unanswered)
   * Coordinate expert assignments
   * Review reports
   * Manage tenants, accounts, and master data

4. **Government Staff (Municipality)**

   * View usage dashboards
   * Search and view parent/child records

5. **System Admin**

   * Manage system configuration, permissions, and security

---

# 🧭 Main Business Flows

## 0. Setup (Master Data / Pre-configuration)

* Create tenant (municipality)
* Create expert accounts
* Create government staff accounts
* Configure initial verification method (e.g., invitation code, phone verification)

---

## 1. User Onboarding (Parent Registration)

1. Parent completes initial verification (e.g., code provided by municipality)
2. Inputs:

   * parent information
   * child information
3. System generates:

   * family_id
   * child_id
4. Parent logs into the system

---

## 2-A. Chat Consultation (via LINE)

⚠️ Chat does NOT happen inside the web app, but via LINE

Flow:

1. Parent links LINE account (via LINE Login or friend add)
2. Parent sends message via LINE
3. LINE sends webhook to backend
4. Backend:

   * stores message
   * creates or updates chat session
   * assigns expert
5. Expert replies via web portal
6. Backend sends reply back to parent via LINE Messaging API

👉 The system acts as:

* case management system
* message storage
* routing/assignment engine

---

## 2-B. Online Consultation (Video)

1. Parent books appointment
2. System sends:

   * meeting link (e.g., Zoom)
   * questionnaire link
3. Parent fills questionnaire
4. Consultation session happens
5. Expert records consultation notes

---

## 3. Development Assessment

Same as online consultation, plus:

6. Operator reviews report
7. Report is published
8. Parent can view results

---

# 🔁 Additional Flows

* Monthly reporting to municipalities
* Usage dashboards
* Child record (カルテ) viewing

---

# 💡 System Nature

This is essentially a:

👉 **Multi-tenant consultation & case management platform**

* Chat handled via LINE (external channel)
* Video consultation system
* Assessment and reporting workflow
* Centralized case tracking and coordination

---

# ⚙️ Key Technical Requirements

* Multi-tenant architecture (each municipality = tenant)
* Role-based access control (RBAC)
* Audit logging (who accessed/modified data)
* LINE integration (webhook + Messaging API)
* Appointment scheduling system
* Report workflow (draft → review → publish)

---

# 🎯 Planned Tech Stack

* Frontend: React
* Backend: Node.js
* Database: PostgreSQL
* Hosting: AWS
* Integrations:

  * LINE Messaging API (chat)
  * Email (SES)
  * Video (Zoom or similar)

---

👉 Please help me with:

* system architecture design
* database schema (ERD)
* API design
* or optimizing business workflows
```

