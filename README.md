# ClassPulse — Multimodal Attendance & Engagement Agent (Prototype)

A privacy-conscious, browser-based demo for classroom attendance and engagement workflows.

## Run locally
1. Extract the ZIP.
2. Open a terminal in this folder.
3. Run `python -m http.server 8000`
4. Visit http://localhost:8000

Camera access requires localhost or HTTPS and browser permission.

## Included in this prototype
- Responsive instructor dashboard
- Editable class roster and manual Present / Late / Absent status
- CSV attendance export
- Start/end class sessions with local session history
- Local camera preview (no upload, recording, or face recognition)
- Engagement dashboard and explainable sample teaching suggestions
- Browser-local persistence via localStorage

## Important implementation boundary
This is a working front-end MVP, not a production multimodal AI system. The roster is sample data and the engagement percentages/recommendations are illustrative/rule-based. It does not perform face recognition, identity matching, gaze tracking, emotion recognition, speech transcription, or automatic attendance decisions.

## Suggested next engineering milestones
1. Backend: FastAPI + SQLite/PostgreSQL with authentication, role-based access, audit logs, and retention controls.
2. Attendance: consented face detection / identity verification with an enrolled roster, thresholding across multiple frames, and a manual correction workflow. Prefer local processing; do not store raw video by default.
3. Audio: optional on-device voice activity / classroom-level speech activity metrics; avoid speaker identification unless strictly necessary and consented.
4. Engagement: use explicit signals (polls, quiz answers, hand raises, task completion) rather than inferring learning or emotion from faces.
5. Agent: connect a locally hosted model or approved LLM endpoint to anonymized aggregate metrics; provide evidence and human-reviewable recommendations.
6. Tests: test lighting, occlusion, camera failure, false positives/negatives, accessibility, and privacy controls before any real classroom use.

## Privacy note
Obtain informed consent and institutional approval before collecting student data. Follow applicable Indian data-protection requirements and institutional policy. Never use engagement scores as the sole basis for grading or disciplinary decisions.
