# Joint — Job Application & Career Management

Joint is a personal workspace for organizing a job search from the first application through the final hiring decision. Track application progress, prepare for each recruitment stage, manage recruiter relationships, and keep important follow-ups and deadlines in one place.

## Open Joint

**Live application:** [https://joint-frontend-olive.vercel.app/](https://joint-frontend-olive.vercel.app/)

Most workspace pages require you to sign in. If you do not have an account yet, use the registration option on the sign-in page.

### Pages

| Page | Open | What it is for |
| --- | --- | --- |
| Sign in / Sign up | [Open authentication](https://joint-frontend-olive.vercel.app/auth) | Sign in to an existing account or create an account to access your workspace. |
| Dashboard | [Open dashboard](https://joint-frontend-olive.vercel.app/dashboard) | Get an at-a-glance view of your job search: application totals, active applications, interviews, offers, recruitment funnel, recent applications, and upcoming items. |
| Applications | [Open applications](https://joint-frontend-olive.vercel.app/applications) | Create and find applications, filter by recruitment status, browse paginated results, and switch to archived applications. |
| Application detail | [Open an example application](https://joint-frontend-olive.vercel.app/applications/app-1) | Review one application’s information and manage its recruitment workflow. Replace `app-1` in the URL with an application ID from your account; the example ID may not exist in your data. |
| Companies | [Open companies](https://joint-frontend-olive.vercel.app/companies) | Keep a searchable directory of companies associated with your job search. |
| Contacts | [Open contacts](https://joint-frontend-olive.vercel.app/contacts) | Store and manage recruiter, interviewer, and other professional contact details. |
| Reminders | [Open reminders](https://joint-frontend-olive.vercel.app/reminders) | Review upcoming or completed reminders, create new ones, mark them complete, snooze them, or remove them. |

## Features

### Dashboard and job-search overview

The dashboard summarizes your application pipeline with counts for all applications, active applications, interviews, and offers. Its recruitment funnel shows how applications progress through their stages, while status summaries and recent-application information make it easier to spot what needs attention. Upcoming items help you keep track of the next steps in your search.

### Application tracking

Each application connects a role to a company and records information such as:

- Position, application date, and recruitment status.
- Priority, from low through critical.
- Application source, such as a job board, company career page, referral, recruiter, or campus source.
- Employment type, work arrangement, and location.
- Optional salary range, job-posting URL, application-portal URL, and job description.

The applications page supports keyword search, status filters, archived-application filtering, and pagination. Available statuses cover the job-search lifecycle, including wishlist, applied, in review, assessment, interview, offer, hired, rejected, withdrawn, on hold, and ghosted. Open an application to access its complete record and workflow tools.

## Application detail: manage the full recruitment process

An application detail page brings together the role, its progress, preparation work, and activity history. The header shows the current status and priority alongside the company, position, application date, and any saved location, employment type, work arrangement, source, or salary range. From the same page, you can change the status, edit the application, archive or unarchive it, or delete it. Saved job and application links open the corresponding external pages, and the job description can be expanded when needed.

### Roadmap

Use the roadmap as a stage-by-stage plan for a specific application. Create a roadmap when one does not exist, then add, edit, or remove stages to reflect the employer’s recruitment process. Each stage can include a description, scheduled date, and notes.

Stages have statuses such as pending, in progress, completed, or skipped. Mark stages complete as you move forward; the roadmap displays a completion count and progress percentage so you can quickly see how much of the process is done. A custom roadmap can be adjusted to match the actual hiring process instead of forcing every application into the same sequence.

### Stage tasks, interview preparation, and scheduling

The **Stage Tasks** tab keeps preparation and interview-related items tied to roadmap stages. Create and edit items, associate them with a stage and category, and filter the list by item group or stage. Items can include a title and notes, priority, assignee, location, a URL, and scheduled date and time with a time zone. Track work with todo, in-progress, done, or cancelled statuses.

This makes it possible to keep practical next steps—such as preparing materials, completing an assessment, or planning an interview—alongside the recruitment stage they belong to.

### Follow-ups

Plan communication with recruiters or hiring teams in the **Follow-up** tab. Record a follow-up date, channel (email, LinkedIn, WhatsApp, phone, or another channel), and an optional message or plan. Edit planned follow-ups, mark them complete, and record the result of the conversation. When appropriate, set a next follow-up date to keep the communication cycle moving.

### Notes

Use the **Notes** tab to capture application-specific context, such as interview observations, questions to ask, or details to remember. Add notes as the process evolves and remove notes that are no longer relevant.

### CV upload, extraction, and analysis

The **CV** tab stores CV profiles against an individual application, so the document and its insights remain associated with the role. Upload a CV as a PDF. The extraction process runs automatically, and the profile list shows the file name and processing status. Open a profile to inspect its extracted information and analysis.

The extraction view organizes information found in the document, including:

- Candidate name and email.
- Work experience, company, position, dates, responsibilities, and technologies used.
- Education, institution, degree or field of study, dates, and GPA when available.
- Projects, project role, description, and technologies.
- Skills grouped from technical skills, soft skills, and tools.

After extraction has completed, start CV analysis from the profile detail. The analysis view presents a generated summary together with identified strengths and weaknesses. Processing status is shown while extraction or analysis is underway, and the interface reports failures so you can take action, including uploading a CV again when extraction fails.

### Timeline and application history

The timeline on the detail page provides a chronological activity record for the application. Events can include status changes, with the previous and new statuses shown together, as well as an event description and date when available. This helps you retrace how the application has progressed.

### Application lifecycle controls

Update the application status as it moves through recruitment, edit its saved details, and archive applications that you want to keep without showing in the active list. Archived applications can be found using the archive filter. Deletion is available from the detail page and requires confirmation.

## Other workspace pages

### Companies

Maintain company records with details such as name, industry, location, and website. Search the directory, add a company while managing your records, edit details, or remove a company.

### Contacts

Keep recruiter, interviewer, and other professional details together. Contact records can include a name, role, email address, phone number, LinkedIn URL, and notes. Search, add, edit, and delete contacts as your network changes.

### Reminders

Create reminders for interviews, assessment deadlines, follow-ups, application deadlines, recruitment stages, periods without updates, or custom events. Set a due date and optional message. The page can show active reminders or all reminders; mark an item complete, snooze it until a later date, or delete it. Overdue and completed items are visually distinguished.

## Frontend and backend

This repository contains the Joint web frontend. It communicates with the API provided by the separate backend repository:

- [Joint backend — joint-backend-nest](https://github.com/fazriridwan19/joint-backend-nest)

The frontend reads the backend base URL from `VITE_BACKEND_BASE_URL`. Configure it to point to a running, reachable backend for local development or another deployment environment.

## Run locally

### Requirements

- Node.js and npm.
- A running Joint backend that the frontend can reach.

### Setup

1. Install dependencies:

   ```bash
   npm install
   ```

2. Create a local environment file from the example. In PowerShell:

   ```powershell
   Copy-Item .env.example .env.local
   ```

3. Set `VITE_BACKEND_BASE_URL` in `.env.local` to the backend API URL. The example value is `http://localhost:8080/api/v1`.

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Open the local URL printed by Vite, usually [http://localhost:5173](http://localhost:5173).

## Available scripts

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Vite development server. |
| `npm run build` | Run the TypeScript project build and create a production build. |
| `npm run preview` | Preview the production build locally. |
| `npm run lint` | Run Oxlint. |
