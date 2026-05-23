# LeadRichmentAI

A professional, enterprise-ready lead enrichment platform that automates lead capture, website intelligence, AI-powered analysis, PDF audit generation, and email delivery.

## Overview

LeadRichmentAI is a full-stack prototype built with:
- **Next.js + TypeScript** for the frontend
- **Express + TypeScript** for the backend
- **Playwright + Cheerio** for resilient scraping
- **Groq + Gemini** for AI analysis
- **Puppeteer** for PDF generation
- **Nodemailer** for email delivery

The application is designed to run end-to-end with minimal manual intervention and optional Google Sheets/Drive integration.

## Quick Start

### Install dependencies

```bash
npm run install:all
```

### Run in development

```bash
npm run dev
```

The frontend runs on `http://localhost:3000` and the backend runs on `http://localhost:5000` by default.

## Configuration

Copy `backend/.env.example` to `backend/.env` and set the required values.

### Required variables

- `PORT` — backend port
- `FRONTEND_URL` — frontend origin
- `GROQ_API_KEY` or `GEMINI_API_KEY` — at least one AI provider key
- `SMTP_HOST` — SMTP server host
- `SMTP_PORT` — SMTP port
- `SMTP_USER` — sender email address
- `SMTP_PASS` — app password for Gmail
- `EMAIL_FROM` — displayed sender name

### Optional Google integration

Set `ENABLE_GOOGLE_INTEGRATIONS=true` and provide Google Sheets/Drive credentials only if you want optional logging and archiving.

## Project Structure

- `backend/` — API server, workflow orchestration, scraping, AI providers, PDF/email services
- `frontend/` — landing page, lead form, real-time workflow status, UI components
- `backend/.env.example` — example environment variables
- `frontend/.eslintrc.json` — frontend lint configuration
- `package.json` — root commands for install, development, build, and start

## Available Scripts

```bash
npm run install:all      # install backend and frontend dependencies
npm run dev              # run frontend and backend concurrently
npm run build            # build both backend and frontend
npm run start            # start both services in production mode
```

## Notes

- The backend uses **Server-Sent Events** to stream workflow status updates to the UI.
- The scraping pipeline uses **Playwright first**, with **Cheerio fallback** for sites that fail or time out.
- AI analysis is configured to generate structured business insights, recommendations, and report content from scraped website data.
- The PDF generator produces a clean audit-style report and attaches it to email delivery.

## Additional Documentation

See the project documentation files for more details:
- `SETUP.md`
- `API_DOCS.md`
- `ASSUMPTIONS.md`
- `TRADEOFFS.md`
- `SECURITY.md`
- `TESTING.md`
- `SUBMISSION.md`

## License

MIT
