# cyber-ttx-platform

**AI-Enabled Cybersecurity Tabletop Exercise (TTX) Platform**

A web-based, choose-your-own-adventure style application for creating, running, and documenting realistic cybersecurity tabletop exercises with full fidelity to CSIRT / incident response processes.

- **Dynamic LLM-driven gameplay**: xAI Grok API (recommended) or local Ollama. Generates branching injects, multiple-choice options with realistic outcomes (insight / partial / distraction / dead-end), and free-response evaluation.
- **CSIRT-native**: Track participants, declare reportable incidents, stand up CSIRT, assign roles (Incident Commander, Ops/Technical Lead, Comms, Legal, Intel, PR, Scribe, etc.). Everything is logged.
- **Complete audit trail**: Every action, communication, decision, note, and role change is timestamped in the recorder log.
- **Professional deliverables at the end** (and on-demand):
  - Recorder Log (full chronological)
  - After Action Report / Improvement Plan (AAR/IP) following CISA/NIST-style templates
  - Executive Summary / Memo
- **Modern GUI**: All interactions (setup wizard, live runner with choices + notes + modals, live roster/log, export) happen in the browser. Shareable exercise sessions.
- **Built with the harness**: This project was bootstrapped using the GitHub MCP connector and is intended to be developed following Grok superpowers (brainstorming, design, execute-plan, TDD, verification, worktrees) + bundled skills.

**GitHub**: https://github.com/arkhala/cyber-ttx-platform (created via `grok_com_github` MCP tools).

## Quick Start (after full implementation)

```bash
# 1. Clone
git clone https://github.com/arkhala/cyber-ttx-platform.git
cd cyber-ttx-platform

# 2. LLM config (pick one)
cp .env.example .env
# Edit .env:
#   XAI_API_KEY=your_xai_key          # for Grok
#   # OR
#   OLLAMA_BASE_URL=http://localhost:11434
#   OLLAMA_MODEL=llama3.2

# 3. Run (Docker recommended)
docker compose up --build

# Or local:
# Backend: cd backend && pip install -e . && uvicorn app.main:app --reload
# Frontend: cd frontend && npm install && npm run dev
```

Open http://localhost:3000 (or backend-served UI) and start a new exercise.

See the generated docs in `exports/` after completing a scenario.

## Key Features Implemented (target)

- Scenario presets + freeform AI generator
- Multi-participant + role assignment UI
- "Is this reportable?" prompts at natural points
- CSIRT stand-up flow + live role matrix
- Freeform notes + comms logging anytime
- AI options with varied consequences
- Full state persistence + resume
- End-of-exercise document generation via docx skill + LLM synthesis
- Exportable JSON transcript for replay

## Tech Stack (as planned)

- Backend: Python + FastAPI, Pydantic, SQLite (or JSONL), python-docx integration (via ~/.grok skills)
- LLM: xai-sdk or OpenAI-compatible client (Ollama)
- Frontend: Next.js (or HTMX+Alpine fallback) + Tailwind, real-time via WS
- Docs: Integrated docx generation + templates
- Container: Docker Compose for one-command run
- Dev process: design skill → execute-plan (worktree-isolated PRs) → reviews → GitHub PR stack

## Development Notes

This repo was created empty via the GitHub MCP connector (`grok_com_github__create_repository` + `get_me`) as the very first step after plan approval.

Further implementation follows the approved plan in the session (see `.grok/sessions/.../plan.md` in the originating workspace) and the design document that will be generated under `docs/`.

Contributions and exercises are welcome. Run your own TTXs, improve scenarios/prompts, or extend the CSIRT flows.

## License

MIT (see LICENSE)

## Acknowledgments

Inspired by CISA CTEP packages, NIST SP 800-61, real CSIRT tabletop practice, and the power of structured AI facilitation + rigorous harness-driven development.

---

**Status**: Repo bootstrapped + plan approved. Design + implementation in progress via Grok Build.
