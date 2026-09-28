# Sahakar Setu (सहकार सेतु) — SIH 2026 Documentation

**Multilingual Cooperative Governance & Legal Assistance** · Smart India Hackathon 2026 · PS 26088 (Ministry of Cooperation / NCCT) · Team **LexNova** (ID 131559) · Theme: Agriculture, FoodTech & Rural Development · Mode: Software + Hardware

## Live Demos
| Artifact | Link |
|---|---|
| IVR voice assistant (Hindi, feature phone) | **+1 346 998 6840** |
| Production server (health/API) | https://sahakar-setu-server.onrender.com (`/health` → `{status: ok, db: connected}`) |
| Web chat / PWA | https://sahakar-setu-ai.vercel.app/ |
| Demo video | *[YouTube link]* |

## Dataset
- [Sahakar Setu Corpus on HuggingFace](https://huggingface.co/datasets/ismailmo9090/SahakarSetu_Corpus) — 333 knowledge passages + 13-query eval set

## Documentation
- [Technical Approach](Technical_Approach.html) — RAG engine deep-dive with code
- [Voice AI](Voice_AI.html) — IVR (Vapi), Vosk STT, TTS fallback chain
- [Grievance Module](Grievance_Module.html) — Hindi templates, tracking, escalation
- [Kiosk Hardware](Kiosk_Hardware.html) — BOM, power budget, cost
- [PDF copies](pdfs/) — submission-ready detail docs
