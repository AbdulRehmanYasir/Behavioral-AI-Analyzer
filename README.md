<div align="center">

# BEHAVIORAL AI ANALYZER

### Privacy-Focused Writing Behavior Analysis

A browser-based writing behavior analyzer that examines typing patterns, editing activity, paste behavior, input rate, and content characteristics to generate behavioral insights and heuristic human/AI assessments.

</div>

---

## Overview

**Behavioral AI Analyzer** is a privacy-focused browser application designed to analyze **how text is produced**, rather than relying only on the final written content.

The application observes writing behavior such as typing speed, keystroke activity, pauses, editing patterns, paste activity, and content characteristics. These signals are combined to generate behavioral metrics, scores, explanations, and an overall assessment.

The entire analysis is designed to run locally inside the browser.

> **100% local — nothing leaves this browser.**

> **Important:** Behavioral AI Analyzer is a heuristic analyzer, not a trained machine-learning model. Its results represent behavioral signals and should not be treated as definitive proof of human- or AI-generated text.

---

## Core Features

* ⌨️ **Typing Behavior Analysis** — Track typing activity, keystrokes, typing speed, pauses, bursts, and session behavior.
* 🤖 **Human / AI Assessment** — Generate Human Score, AI Score, confidence, and an overall behavioral assessment.
* 📋 **Paste Detection** — Detect pasted content and calculate paste-related behavioral signals.
* ✏️ **Editing Activity** — Track Backspace and Delete activity and identify editing patterns.
* 📊 **Input Rate Visualization** — Visualize writing activity over the duration of a session.
* 🧬 **Content Fingerprint** — Analyze content characteristics and display a visual behavioral fingerprint.
* 🕒 **Activity Timeline** — Display important events throughout the writing session.
* 🔍 **Why This Verdict** — Explain the behavioral signals that contributed to the assessment.
* 📝 **Content Analysis** — Analyze text characteristics including words, sentences, repetition, and phrase patterns.
* 🕘 **Session History** — Maintain previous analysis sessions within the application.
* 📤 **JSON Export** — Export analysis information and behavioral data as JSON.
* 📄 **PDF Export** — Generate a PDF report containing analysis results.
* 📋 **Copy Summary** — Copy the generated analysis summary for external use.
* 🔒 **Privacy Focused** — Perform analysis locally without requiring writing content to be uploaded to an external server.
* 📱 **Responsive Interface** — Provide a usable experience across desktop and smaller screen sizes.
* ⚡ **Event Protection** — Bound behavioral event history and prevent excessive keyboard auto-repeat events from overwhelming the application.

---

## Behavioral Analysis

Behavioral AI Analyzer evaluates multiple categories of signals.

### Typing Signals

* Typing speed
* Keystroke activity
* Input frequency
* Writing bursts
* Pauses
* Session duration

### Editing Signals

* Backspace activity
* Delete activity
* Editing bursts
* Cursor movement
* Changes during the writing session

### Input Signals

* Typed characters
* Pasted content
* Dropped text files
* Paste ratio
* Input source distribution

### Content Signals

* Word characteristics
* Sentence characteristics
* Word repetition
* Phrase patterns
* Content fingerprint

These signals are combined to produce the application's behavioral assessment.

---

## Analysis Workflow

The analyzer follows a client-side processing pipeline:

```text
User Writes / Pastes Text
          ↓
Behavioral Events Collected
          ↓
Typing & Editing Analysis
          ↓
Paste & Input Analysis
          ↓
Content Analysis
          ↓
Behavioral Scoring
          ↓
Evidence & Explanations
          ↓
Human / AI Assessment
          ↓
Visualization & Export
```

The system intentionally separates **behavioral evidence** from certainty.

---

## Analysis Summary

The application provides a summary containing:

* Overall assessment
* Human Score
* AI Score
* Confidence
* Typing behavior
* Paste behavior
* Editing behavior
* Evidence count
* Behavioral explanation
* Session information

When there is not enough behavioral evidence, the analyzer can report:

**Insufficient Data**

rather than presenting a misleading high-confidence result.

---

## Stability & Performance

Behavioral event collection is protected against excessive browser keyboard auto-repeat.

The application includes:

* Maximum behavioral event history
* Debounced expensive analysis
* Protection against repeated Backspace/Delete events
* Protection against repeated printable-key events
* Immediate lightweight character and word counters
* Bounded event processing
* Safer analysis updates during high-frequency input

This prevents long-held keyboard actions from continuously creating an unbounded number of behavioral events.

---

## Technology Stack

* **Frontend:** React
* **Language:** TypeScript
* **Styling:** Tailwind CSS
* **Routing / Application Framework:** TanStack Router / Start
* **Charts:** Recharts
* **Animation:** Framer Motion
* **PDF Generation:** jsPDF
* **Build Tool:** Vite
* **Package Management:** npm

---

## Project Structure

```text
Behavioral-AI-Analyzer/
├── public/
│
├── src/
│   ├── components/
│   │   ├── Charts.tsx
│   │   └── ...
│   │
│   ├── lib/
│   │   ├── analyzer.ts
│   │   └── ...
│   │
│   ├── routes/
│   │   └── index.tsx
│   │
│   ├── App.tsx
│   └── ...
│
├── package.json
├── package-lock.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

---

## Running Locally

### Requirements

* Node.js
* npm

### Install Dependencies

```bash
npm install
```

### Start Development Server

```bash
npm run dev
```

The development server will start using the configured Vite development environment.

---

## Production Build

Create a production build with:

```bash
npm run build
```

The production output is generated by the Vite build system.

To preview the production build locally:

```bash
npx vite preview
```

---

## Production Deployment

The application is deployed as a production web application through Vercel.

Live deployment:

**https://behavioral-ai-analyzer.vercel.app/**

For a new deployment, push changes to the configured production branch:

```bash
git add .
git commit -m "Update Behavioral AI Analyzer"
git push
```

Vercel can then build and deploy the updated application from the repository.

---

## Deployment Compatibility

Behavioral AI Analyzer is a client-side React / TypeScript application built with Vite.

The repository does not require generated build directories or installed dependencies to be committed.

Generated and development files should remain excluded through `.gitignore`, including:

* `node_modules/`
* Build output
* Environment files
* Logs
* Local development files

---

## Development Validation

The project has been validated locally with:

```text
npm run build  → PASS
```

The production build successfully transforms the application and generates the production bundle.

The current stability implementation also includes protection against excessive keyboard event generation caused by holding keys such as Backspace and Delete.

---

## Performance

The application performs multiple behavioral and content calculations while analyzing a writing session.

To maintain responsiveness, the current implementation includes:

* Debounced analysis updates
* Bounded behavioral event history
* Reduced processing of repeated keyboard events
* Lightweight real-time counters
* Client-side processing
* Optimized event collection

The application may still generate larger JavaScript chunks due to its visualization, animation, PDF export, and application dependencies.

Further optimization opportunities include:

* Dynamic imports
* Code splitting
* Lazy loading
* Dependency optimization
* Further chart rendering optimization
* Reducing unnecessary recalculation during high-frequency input

---

## Security & Privacy

Privacy is one of the primary goals of the project.

The analyzer is designed to process writing behavior locally inside the browser.

The application does not require sending the user's writing content to an external AI detection API.

### Repository Hygiene

The repository should exclude:

* `node_modules/`
* Build output
* `.env`
* `.env.*`
* Log files
* Local development files
* Operating-system metadata

**Never commit API keys, credentials, secrets, private configuration, or sensitive user data to the repository.**

---

## Limitations

Behavioral AI Analyzer is **not a definitive AI detector**.

Behavioral signals can vary between users and writing environments.

For example:

* A user may paste legitimate research material.
* A fast typist may produce text very quickly.
* A writer may heavily edit their work.
* Different keyboards and devices can affect typing behavior.
* Text may have been written elsewhere before being pasted into the application.
* Short sessions may not provide enough behavioral evidence.

Therefore:

> **The analyzer provides signals, not certainty.**

Results should be interpreted as behavioral indicators rather than conclusive evidence.

---

## Deployment Checklist

Before deploying a new release:

1. Install dependencies.
2. Run the production build.
3. Verify the application starts correctly.
4. Test normal typing.
5. Test Backspace behavior.
6. Test Delete behavior.
7. Test holding a normal keyboard key.
8. Test paste functionality.
9. Test text analysis.
10. Test Analyze.
11. Test Reset.
12. Test session history.
13. Test JSON export.
14. Test PDF export.
15. Test Copy Summary.
16. Verify charts and visualizations.
17. Verify responsive layout.
18. Verify the production deployment.

---

## Live Demo

The complete application is deployed on Vercel:

**https://behavioral-ai-analyzer.vercel.app/**

The application demonstrates:

* Real-time writing behavior tracking
* Typing speed analysis
* Human / AI behavioral scoring
* Paste detection
* Editing activity analysis
* Input rate visualization
* Content fingerprinting
* Activity timeline
* Behavioral explanations
* Session history
* JSON export
* PDF export
* Local browser-based processing

---

## Source Code

GitHub repository:

**https://github.com/AbdulRehmanYasir/Behavioral-AI-Analyzer**

---

## Author

**Abdul Rehman Yasir**

BS Artificial Intelligence Student | Developer

Building real-world software & AI projects.

GitHub: https://github.com/AbdulRehmanYasir

---

### Keep Learning. Keep Building. Keep Improving.

**Made with ❤️ by Abdul Rehman Yasir**
