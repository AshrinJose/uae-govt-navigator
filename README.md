# UAE Gov Navigator

An **agentic AI assistant** for navigating UAE government procedures. Describe a life event — relocating for a job, having a baby, registering a car, paying a fine — and **Dalil**, the AI agent, identifies every required government step, orders them by dependency, researches current requirements via live web search, and builds a personalised step-by-step roadmap.

Built for the **GeeksforGeeks × Google "Build with AI"** workshop (UAE).

🔗 **Live demo (deployed on Vercel):** `https://your-project.vercel.app`

---

## Why it matters

The UAE has committed to moving **50% of government services to agentic AI within two years**. The headline example officials cite is exactly a life event — someone changing jobs whose visa, Emirates ID, and related services are handled as a single intent rather than many separate applications. This project is a working demonstration of that pattern, applied across **federal (ICP, GDRFA, MOHRE), Abu Dhabi (TAMM), and Dubai (Dubai Now)** authorities — a vendor-neutral, cross-emirate planning layer for someone who hasn't yet entered any single government ecosystem.

---

## How it's agentic

Dalil is an **orchestrated chain of agents**, each passing structured state (JSON) to the next:

1. **Journey Mapper** — identifies the required procedures and sequences them by real UAE dependency (e.g. work permit → entry permit → medical → Emirates ID → residence visa).
2. **Requirements Researcher** — uses Gemini's **`google_search` tool** to fetch current documents, fees, and processing times (live tool use).
3. **Plan Builder** — combines everything into an ordered roadmap, including which **typing/service centre** (Tasheel, Amer, TAMM) each step can be done at, alongside the self-service portal.

The live **agent trace** shows each step planning, working, and completing in real time.

---

## Features

- Life-event input with quick-pick prompts and contextual follow-ups
- Fit-for-purpose roadmap: authority, documents, fee, time, where to do it, official link, dependencies
- Emirate selector (Abu Dhabi / Dubai / Other) and bilingual output (English / Arabic / Both)
- Follow-up chatbot scoped to the generated plan
- AEGOV-inspired UAE government design, dark mode
- Manual-only API calls to conserve free-tier quota

---

## Tech stack

| Layer | Choice |
|---|---|
| LLM | Google Gemini API (`generateContent`) |
| Tool use | Gemini `google_search` grounding |
| Frontend | Single-file HTML / CSS / JS |
| Deployment | **Vercel** (static, user supplies their own Gemini key) |

---

## Run it

1. Open the live URL (or `index.html` locally).
2. Paste a free Gemini API key from [aistudio.google.com](https://aistudio.google.com) and click **Connect**.
3. Pick an emirate, describe your situation, and click **Run agent**.

---

## Note on accuracy

This is an independent planning aid, **not affiliated with any UAE government entity**. Fees and procedures change and vary by nationality, emirate, and centre — every step links back to the official portal (u.ae, TAMM, ICP, GDRFA) for verification.


