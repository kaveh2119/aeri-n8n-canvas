# READ ME FIRST · AERI Research Ecosystem
**A supervised review engine for research manuscripts and proposals, built in n8n.** 43 AI agents check a draft against the data, the physics and the literature. The researcher decides every change and every release. The same engine serves manuscripts, reviewer responses, proposals, funding strategies, white papers and briefings.

## How one version moves through the engine
1. **Intake.** Configuration, Gemini notebooks, governing instructions and the researcher's standing rulings are loaded.
2. **Engineers (accuracy).** Numbers, analysis depth, journal fit, overlap with earlier papers, physical limits.
3. **Critics (rigor).** Literature (answered only from the project's notebooks), referee view, voice, flow, methods.
4. **Citation and quote check.** A script matches every cited passage to the source text.
5. **Verification.** A verifier tries to disprove each finding; a completeness check looks for anything missed.
6. **Plan.** Data findings are rebuilt from the data files; the proposer writes one issue register, one plan and at most two questions.
7. **Gate 1: the researcher decides.** Accept, reject or annotate each item. Every ruling becomes a binding rule.
8. **Re-analysis** of data, physics and literature under those rulings.
9. **Section loop R1-R7.** Each section is revised in turn, up to three rounds, with section-level critics.
10. **Assembly** and a whole-paper critic.
11. **Version round.** Open findings are resolved with data or literature before the author sees them.
12. **Outside reviewer.** A Gemini Gem grounded in funded NSF awards reviews the version; only verified findings are kept.
13. **Exit gates by script.** Overlap, citations, sentence length and claim trace.
14. **Researcher signs off.** If not approved, the evolve step tightens the rules and the round runs again.
15. **Library.** Rules, rulings, the decision log and one Gem pack per role are kept for the next project.

## Three safeguards
- A data claim must cite a data cell or show its calculation, or it is discarded.
- A finding is acted on only after an independent attempt to disprove it.
- No version is released without the researcher's approval.

## Models and status
- **Gemini Pro latest** (today Gemini 3.1 Pro) for deep-reasoning lanes and **Gemini Flash latest** (today Gemini 3.8 Flash) for mechanical lanes. Both names move to Google's newest model on release, so a new Gemini needs no edit. **Gemini Notebook** for literature. A second-family verifier is available and switched off.
- ✅ marks parts already tested in a full manuscript revision (on Claude models; see Track record). 🔷 marks parts that are new and set up for the Gemini pilot. The full loop has not yet run end to end on Gemini.

## Reading the canvas
Three rows of rooms, read left to right, one room per stage. Colour shows what a room protects: blue accuracy (engineers), orange rigor (critics), purple reliability (verification), yellow the draft (proposer), red the researcher's decisions, green Gemini Notebook and Gems, grey set-up and library. Each row has its own Gemini model boxes underneath.

## 3D office view
Open **https://YOUR-N8N-ADDRESS/webhook/aeri-office** while this workflow is active. The office shows the same 43 agents in eight departments. During a run, the room doing the work lights up and the researcher's desk turns gold when a gate is waiting. It shows names, counts and the current step only, never manuscript text or data.

## Editing
The office is rebuilt from this workflow every time it opens. Rename, add or switch off an agent, or change the model in an AI Model box, then reload the office. Each agent's **Notes** (node settings) hold two lines the office reads: `Role:` the one-sentence job shown in the office, and `Room:` its department (Engineering, Critics, Verification, Writing Studio, Outside Review, Evolve Lab).

## Track record
The engine revised the 7EMP energy-pile manuscript (D1) from version v22 to v35 on Claude models, 3-4 October 2026. The workflow file still carries that project's draft and data as its working example.

## Set-up (once)
1. **Gemini key:** aistudio.google.com, then Get API key. Add it as the credential on every AI Model box.
2. **n8n key:** Settings, then n8n API, then Create an API key. Add it to **Read Runs** and **Read Workflow** as Header Auth (name `X-N8N-API-KEY`).
3. Switch the workflow to **Active**. Start a run from **Start**.

## This repository
- `index.html` is the 3D office (walk-through), published at https://kaveh2119.github.io/aeri-n8n-canvas/
- `rooms/` holds the room pictures shown on the n8n canvas.
