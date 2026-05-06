# AceNORCET — AIIMS Nursing Officer Exam Prep

A free, mobile-first mock test platform for nursing professionals preparing for the **AIIMS NORCET (Nursing Officer Recruitment Common Eligibility Test)** examination.

---

## Features

- **Three Test Modes**
  - Nursing Fundamentals — 20 questions, 20 minutes
  - General Knowledge & Aptitude — 20 questions, 20 minutes
  - Full Mock Test — 100 questions, 90 minutes

- **Real Exam Simulation**
  - Countdown timer with auto-submit
  - Questions shuffled randomly each attempt
  - Live question-by-question progress tracker

- **NORCET-style Marking Scheme**
  - +1 for every correct answer
  - −⅓ for every wrong answer (negative marking)
  - 0 for skipped questions

- **Result & Score Tracking**
  - Detailed breakdown: correct, wrong, skipped, score
  - Celebratory confetti animation for high scores (≥ 70%)
  - Personal best / high score saved locally per test type

- **Progressive Web App (PWA)**
  - Installable on Android and iOS via "Add to Home Screen"
  - Offline caching via service worker

- **Clean, Responsive UI**
  - Mobile-first design using Tailwind CSS + shadcn/ui
  - Smooth animations powered by Framer Motion

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, TypeScript, Vite |
| Routing | Wouter |
| Styling | Tailwind CSS, shadcn/ui (Radix UI) |
| Animations | Framer Motion |
| State | TanStack React Query |
| Backend | Node.js, Express, TypeScript |
| ORM | Drizzle ORM |
| Database | PostgreSQL |
| PWA | Service Worker, Web App Manifest |

---

## Scoring Formula

Score = (Correct × 1) + (Wrong × −0.333)
Percentage = (Score / Total Questions) × 100

Scores ≥ 70% trigger a confetti celebration and are recorded as a new personal best.

---

## Disclaimer

This platform is independently developed and is **not affiliated with AIIMS or the National Testing Agency (NTA)**. All questions are for practice purposes only.
