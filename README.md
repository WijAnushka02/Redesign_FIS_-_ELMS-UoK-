# ELMS — Redesign of the Faculty Information System

A redesigned, secure, and intelligent academic portal for the Faculty of Science, replacing the legacy Faculty Information System (FIS). ELMS provides accurate GPA calculation, GPA simulation, degree classification tracking, personalized exam timetables, draft transcript generation, and an AI-powered academic guidance chatbot with voice support — built with role-based dashboards for students, lecturers, academic advisors, examination officers, and administrators.

**Design reference:** [Stitch AI wireframes / Figma prototype](https://stitch.withgoogle.com/projects/12483674484002546498)

---

## 📖 Project Description

The current Faculty Information System is limited to basic result viewing and suffers from usability, security, performance, and accessibility issues. This project redesigns it into a modern, responsive, scalable, and AI-supported academic portal.

Students will be able to view examination results, track semester and cumulative GPA, simulate future grades, monitor degree classification progress, download draft transcripts, access personalized exam timetables, and get AI-driven academic guidance (including voice commands). Lecturers and administrators get live update tools, course performance analytics, and secure academic management functions.

### Problem Statement
The existing FIS has weak authentication, an outdated interface, inaccurate GPA calculations, no academic planning tools, poor performance under load, and limited mobile responsiveness. Students receive no guidance on what grades they need to reach a target GPA or degree classification, and lecturers have no way to push live updates or monitor course performance.

### Main Objective
Design and develop a modern, secure, responsive, scalable, and intelligent Faculty Information System for the Faculty of Science that supports both students and academic staff through role-based dashboards and analytical tools.

---

## ✨ Key Features

- **Student Dashboard** — GPA, credits, results, timetable, and AI suggestions at a glance
- **Secure Login & Account Management** — MFA, account lockout, CAPTCHA, password reset
- **Role-Based Access Control** — Student, Lecturer, Academic Advisor, Examination Officer, System Administrator
- **Examination Results Page** — filter, search, sort, and export results by year/semester
- **Draft Transcript Generation** — watermarked, QR-verified PDF up to the latest published results
- **Accurate GPA Engine** — semester & cumulative GPA following official university rules
- **GPA Simulator & Academic Target Calculator** — "what grade do I need to reach GPA X?"
- **Degree Classification Progress Tracker** — visual progress toward First Class, Second Upper, etc.
- **AI Academic Guidance Chatbot** — rule-based + ML + generative AI hybrid, with **voice command support** (speech-to-text / text-to-speech)
- **Local-Running AI Module** — offline/local LLM runtime option for privacy-sensitive or offline use
- **Course Difficulty & Performance Dashboards** — pass rates, grade distribution, trend charts
- **Lecturer Live Update System** — real-time announcements, marks, and course updates
- **Early Academic Support System** — flags at-risk students privately, without negative labeling
- **Personalized Examination Timetable** — filtered to the student's registered courses
- **Notifications** — in-system, email, SMS, and push
- **Mobile-Responsive & Accessible** — WCAG 2.1 AA target, multi-language support (English, Sinhala, Tamil)

---

## 🛠️ Tools & Technologies

### Frontend
- React / Next.js
- TypeScript
- Tailwind CSS or Material UI
- React Hook Form
- Zod (validation)
- Chart.js or Recharts

### Backend
- Spring Boot / Node.js (Express) / ASP.NET Core *(one to be selected)*
- REST APIs
- Role-based access control & secure authentication (JWT, MFA)

### Database
- PostgreSQL or MySQL
- Database indexing, transaction management, audit tables
- Automated backups & data encryption

### AI & Machine Learning
- Python
- FastAPI or Flask
- scikit-learn, pandas, NumPy
- Retrieval-Augmented Generation (RAG)
- Approved LLM integration (with local/offline runtime option)
- Rule-based academic calculation engine

### Real-Time Features
- WebSockets
- Server-Sent Events (SSE)
- Firebase or similar real-time services

### Deployment & DevOps
- Docker
- Nginx
- Redis (caching)
- Load Balancer
- GitHub Actions (CI/CD)
- Centralized logging & system monitoring

### Design
- Figma / Stitch AI (wireframing & prototyping)

---

## 🔐 Security & Privacy

- HTTPS, secure password hashing, RBAC, input validation
- Protection against SQL injection, XSS, CSRF
- Rate limiting, session timeout, account lockout, MFA
- Audit logging for all sensitive actions (including voice-triggered ones)
- Voice data processed locally where possible; raw audio not stored unless necessary and encrypted when it is
- Students only view their own data; lecturers only see students in their own courses
- AI recommendations are advisory only, reviewable, and disclosed as AI-generated

---

## 📁 Project Structure

```
elms-redesign/
├── README.md
├── LICENSE
├── .gitignore
├── .env.example
├── docker-compose.yml
├── docs/
│   ├── project-plan.md
│   ├── requirements/
│   │   ├── functional-requirements.md
│   │   └── non-functional-requirements.md
│   ├── architecture/
│   │   ├── system-architecture.md
│   │   ├── database-schema.md
│   │   └── ai-architecture.md
│   └── screenshots/
│
├── frontend/                          # React / Next.js + TypeScript
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   ├── common/
│   │   │   ├── dashboard/
│   │   │   ├── results/
│   │   │   ├── gpa-calculator/
│   │   │   ├── gpa-simulator/
│   │   │   ├── transcript/
│   │   │   ├── timetable/
│   │   │   ├── chatbot/
│   │   │   └── notifications/
│   │   ├── pages/                     # or app/ for Next.js App Router
│   │   │   ├── login/
│   │   │   ├── student/
│   │   │   ├── lecturer/
│   │   │   ├── advisor/
│   │   │   ├── exam-officer/
│   │   │   └── admin/
│   │   ├── hooks/
│   │   ├── context/
│   │   ├── services/                  # API calls
│   │   ├── utils/
│   │   ├── types/
│   │   └── styles/
│   ├── package.json
│   └── tsconfig.json
│
├── backend/                           # Spring Boot / Node.js / ASP.NET Core
│   ├── src/main/java/.../elms/
│   │   ├── auth/                      # login, JWT, MFA, RBAC
│   │   ├── user/                      # user & role management
│   │   ├── results/                   # exam results module
│   │   ├── gpa/                       # GPA calculation & simulation
│   │   ├── classification/            # degree classification tracker
│   │   ├── transcript/                # draft transcript generation (PDF + QR)
│   │   ├── timetable/                 # personalized exam timetable
│   │   ├── notifications/
│   │   ├── analytics/                 # course/lecturer analytics
│   │   ├── audit/                     # audit logging
│   │   ├── realtime/                  # WebSocket / SSE handlers
│   │   └── config/                    # security, CORS, DB config
│   ├── src/main/resources/
│   │   ├── application.yml
│   │   └── db/migration/              # Flyway/Liquibase scripts
│   └── pom.xml (or package.json for Node)
│
├── ai-service/                        # Python — chatbot, ML, voice assistant
│   ├── app/
│   │   ├── main.py                    # FastAPI entrypoint
│   │   ├── chatbot/
│   │   │   ├── rag_engine.py          # retrieval-augmented generation
│   │   │   ├── prompts/
│   │   │   └── llm_client.py
│   │   ├── rule_engine/               # GPA rules, classification rules
│   │   ├── ml_models/
│   │   │   ├── difficulty_predictor/
│   │   │   ├── pass_rate_forecast/
│   │   │   └── risk_identification/
│   │   ├── voice/
│   │   │   ├── speech_to_text.py
│   │   │   ├── text_to_speech.py
│   │   │   └── voice_command_parser.py
│   │   ├── local_runtime/             # 👈 local-running module (see note below)
│   │   │   ├── local_llm_config.py
│   │   │   ├── offline_model_loader.py
│   │   │   └── README.md
│   │   └── data/                      # approved regulations, reference docs
│   ├── requirements.txt
│   └── tests/
│
├── database/
│   ├── schema.sql
│   ├── seed-data/
│   └── er-diagram.png
│
├── infra/
│   ├── docker/
│   │   ├── frontend.Dockerfile
│   │   ├── backend.Dockerfile
│   │   └── ai-service.Dockerfile
│   ├── nginx/
│   ├── redis/
│   └── k8s/ (optional)
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
│
└── tests/
    ├── frontend/
    ├── backend/
    ├── ai-service/
    └── load-testing/
```

---
