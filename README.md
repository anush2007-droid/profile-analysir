# SkillBridge — Student Skill Development & Internship Portal

A responsive React + Vite demo for students to discover internships, learn practical skills, join portfolio projects, and track career development.

## Features

- Responsive dashboard with learning activity chart and transparent demo readiness estimate
- Internship search, domain/work-mode filters, sorting, save actions, and local demo application tracking
- Learning hub with search, domain filters, and local course progress
- Project hub with join actions
- Editable student profile and profile-strength checklist
- Career guidance roadmap and notification centre
- Local persistence via `localStorage`
- Mobile-friendly sidebar and toast feedback

## Run locally

Requirements: Node.js 18+ and npm.

```bash
npm install
npm run dev
```

Open the local URL printed by Vite (usually `http://localhost:5173`).

Create a production build:

```bash
npm run build
npm run preview
```

## Demo mode and limitations

This project intentionally runs without a backend. Listings and sample statistics are demonstration data, not verified live opportunities. Applications are **not** sent to employers. Profile, saved internships, joined projects, notifications, and course progress are saved in the current browser using `localStorage`.

The login/authentication UI, resume upload/export, project creation, live listings, and recruiter/admin workflows require a backend integration before they can be used securely in production.

## Suggested production setup

1. Create a Supabase project and configure Auth.
2. Add environment variables in `.env` (never commit secrets):

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

3. Add PostgreSQL tables for `profiles`, `courses`, `course_progress`, `internships`, `saved_internships`, `applications`, `projects`, `project_members`, and `notifications`.
4. Enable Row Level Security and policies for every user-owned table. Keep recruiter/admin permissions on the server/database, not just in frontend code.
5. Replace demo arrays and localStorage persistence with authenticated Supabase queries and storage.
6. Add server-side validation and moderation before allowing recruiter-submitted listings to become public.

## Project structure

```text
skillbridge/
├── index.html
├── package.json
├── vite.config.js
├── README.md
├── App.jsx
├── main.jsx
└── styles.css
```

## Technology

- React 18
- Vite 6
- Lucide React icons
- Recharts
- Custom responsive CSS design system

No Tailwind or shadcn/ui configuration is needed for this version; the visual system is implemented in reusable React patterns and CSS.
