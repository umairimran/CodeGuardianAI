# CodeGuardian AI

<p align="center">
  <strong>AI-powered code security and quality analysis, built with IBM Granite.</strong><br />
  Find vulnerabilities earlier. Understand risk faster. Ship with confidence.
</p>

<p align="center">
  <a href="https://ibm-bob-hackathon-nu.vercel.app/">Live demo</a> ·
  <a href="https://github.com/umairimran/CodeGuardianAI">GitHub repository</a>
</p>

## Overview

CodeGuardian AI is a focused code-review companion that turns uploaded source files into a clear, actionable security report. It combines IBM watsonx.ai and Granite models with deterministic fallback checks to surface vulnerabilities, code smells, quality risks, and practical remediation steps in one polished dashboard.

Created for the IBM Build-on-Belief hackathon, it is available as a live web app: **[Open CodeGuardian AI →](https://ibm-bob-hackathon-nu.vercel.app/)**

## What it does

- **Scans source code with IBM Granite** for security and quality concerns.
- **Detects common risk patterns**, including exposed secrets, hardcoded credentials, SQL injection, XSS, weak cryptography, missing validation, and unprotected routes.
- **Prioritizes findings** using Critical, High, Medium, and Low severity levels.
- **Calculates a health score** with security risk, code quality, issue totals, and files analyzed.
- **Explains findings** with location, context, impact, and recommended remediation.
- **Generates actionable AI guidance** with step-by-step fixes.
- **Supports multiple languages**, including Python, JavaScript, TypeScript, Java, Go, Ruby, PHP, C#, C/C++, and Rust.
- **Exports reports as JSON** and falls back to local rule-based analysis when watsonx is unavailable.

## Product flow

```text
Upload up to five files → Analyze with Granite → Review prioritized findings → Download report
```

## Tech stack

| Area | Technology |
| --- | --- |
| Framework | Next.js 14 App Router |
| Language | TypeScript |
| AI analysis | IBM watsonx.ai and Granite models |
| Styling | Tailwind CSS |
| State | Zustand |
| Charts | Recharts |
| Uploads | React Dropzone |
| Icons | Lucide React |

## Run locally

### Prerequisites

- Node.js 18 or newer
- npm
- IBM watsonx.ai credentials for AI-powered analysis

### 1. Clone and install

```bash
git clone https://github.com/umairimran/CodeGuardianAI.git
cd CodeGuardianAI/codescan-ai
npm install
```

### 2. Configure watsonx.ai

Create `codescan-ai/.env.local`:

```env
WATSON_API_KEY=your_ibm_cloud_api_key
WATSON_PROJECT_ID=your_watsonx_project_id
WATSON_URL=https://us-south.ml.cloud.ibm.com
WATSON_VERSION=2023-05-29
```

Create or select a project in [IBM watsonx.ai](https://www.ibm.com/products/watsonx-ai), then add the API key and project ID. Never commit secrets or `.env.local`.

### 3. Start the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

### Production build

```bash
npm run build
npm start
```

## Using the app

1. Add up to five supported source files on the upload screen.
2. Start the analysis.
3. Review the health score, severity distribution, issue categories, code context, and AI insights.
4. Follow the recommended remediation steps.
5. Download the complete JSON report when finished.

## Project structure

```text
codescan-ai/
├── app/
│   ├── api/analyze/       # Analysis API route and fallback logic
│   ├── dashboard/         # Results dashboard
│   ├── upload/            # Upload and analysis screen
│   ├── globals.css        # Global styles
│   └── page.tsx           # Landing page
├── components/Dashboard/  # Charts, metrics, findings, and suggestions
├── lib/                   # Parser, Zustand store, and Watson client
├── types/                 # Shared TypeScript models
└── package.json
```

## Security note

CodeGuardian AI is an assistive analysis tool, not a replacement for a full secure-development lifecycle, professional review, or dedicated security testing. Validate findings before acting on them, and avoid uploading proprietary source code to environments you do not control.

## Contributing

Issues, ideas, and pull requests are welcome. Please include reproducible steps where relevant, and keep credentials and private source code out of commits.

## License

This project is released under the MIT License.

---

Built with Next.js, TypeScript, and IBM watsonx.ai Granite.
