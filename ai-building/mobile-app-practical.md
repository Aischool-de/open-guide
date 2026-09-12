# Mobile app practical session

Timed build sprint for a **working mobile prototype** you can open on an emulator (or device). Prefer one vertical flow over a polished UI.

Use with: [Build loop cheatsheet](./build-loop-cheatsheet) · [Sprint checklist](./sprint-checklist) · [Prompts](/prompts/)

**Default stack for today:** [Expo](https://expo.dev) (React Native) — fastest path from empty folder → emulator. Swap Flutter / native only if your team already knows it.

---

## Session goal

By the end you should have:

1. A scoped mobile MVP (one user · one action · one visible result)
2. An Expo (or equivalent) project running in an **emulator / simulator**
3. One complete on-screen flow with sample data
4. A **60–90 second** demo path rehearsed once

Official Shipaton rules (new app, store release window, RevenueCat, etc.) live on [Devpost](https://revenuecat-shipaton-2026.devpost.com/) and [shipaton.com](https://www.shipaton.com) — don’t burn the practical hour on store submission.

---

## Order of work

| Step | Do this | Prompt below |
|------|---------|--------------|
| 1 | Lock the idea as a short BRD | [Mobile BRD v1](#1-mobile-brd-v1) |
| 2 | Freeze scope before code | [Mobile scope contract](#2-mobile-scope-contract) |
| 3 | Scaffold the app | [Scaffold Expo app](#3-scaffold-expo-app) |
| 4 | Get an emulator running | [Install & run emulator](#4-install--run-emulator) |
| 5 | Build the first vertical slice | [First mobile screen + flow](#5-first-mobile-screen--flow) |
| 6 | If stuck | Use [Unstuck](/prompts/unstuck) with terminal / emulator evidence |
| 7 | Before demo | [Quality gate](/prompts/quality-gate) |

Fill the [Sprint checklist](./sprint-checklist) scope table while you run prompts 1–2.

---

## Stack notes (keep tiny)

- **Expo Go** on a physical phone works if Wi‑Fi allows — emulator is more reliable in a workshop room.
- **iOS Simulator** needs a Mac + Xcode. **Android Emulator** works on Mac/Windows/Linux via Android Studio.
- Don’t add RevenueCat / paywalls until the core flow runs and you still have time.
- One platform for the demo is enough (Android *or* iOS).

---

## Copy-paste prompts

Replace bracketed parts. Paste into Cursor Agent, Claude, ChatGPT, or similar. Prefer an agent that can run terminal commands for steps 3–4.

### 1. Mobile BRD v1

```text
I want to solve [Problem] with a mobile app (iOS and/or Android).

Act as an experienced product manager for mobile products. Create a concise
business requirements document in Markdown for version 1 of this idea.

Your document must use these headings and answer each question explicitly:

1. Who is the user? — primary persona for v1 (one person)
2. What painful job are they doing? — current workflow and friction on mobile
3. What changes after success? — concrete outcome after using the app
4. What is outside version 1? — explicit non-goals (no auth, no social, no
   multiplayer, no store release checklist unless we ask)
5. How will we know it works? — measurable acceptance criteria on device/emulator
6. Mobile constraints for v1 — offline vs online, one primary screen path,
   portrait phone only unless justified

Additional instructions:
- Start with a short executive summary (problem + proposed solution).
- Write in plain language for a mixed technical and non-technical team.
- Assume a timed hackathon: prefer demos that work with sample/local data.
- End with an Assumptions section for anything you inferred.
- If critical details are missing, ask up to 3 clarifying questions first.
  Otherwise, proceed and label assumptions.
```

### 2. Mobile scope contract

```text
We are building a short mobile MVP for a timed practical session. Our scope contract:

- User: [one person]
- Problem: [one painful job]
- Version 1 action: [one action the user takes in the app]
- Visible result: [one thing they see on screen after the action]
- Done when: [one testable statement we can verify on emulator]
- Platform for demo today: [Android emulator / iOS simulator / Expo Go on phone]

Before writing code:
1. Note 2–3 comparable mobile UX patterns (brief bullets).
2. Choose the smallest vertical slice that satisfies "Done when".
3. List screens for v1 (max 3). Mark anything else as deferred.
4. Create short Markdown files in /docs for product brief, requirements,
   architecture, UI notes, build plan, and test notes (mark unknowns TBD).

Show me the plan for approval before scaffolding or implementation.
Do not generate the full app yet.
```

### 3. Scaffold Expo app

```text
Approved scope (do not expand it):
- User: […]
- Problem: […]
- Version 1 action: […]
- Visible result: […]
- Done when: […]

Scaffold a new Expo (React Native) TypeScript app in this folder for that MVP.

Requirements:
1. Use the current recommended Expo workflow (create the project if missing).
2. Keep dependencies minimal — no auth, no navigation library unless required
   for ≤3 screens.
3. Add a README with exact commands to start Metro and open Android / iOS.
4. Create a placeholder home screen that shows the app name and a primary
   button labeled for the Version 1 action (wire it later).
5. Initialize git if not already, with a sensible .gitignore for Expo.
6. After scaffolding, print the exact commands I should run next on my OS.

Ask which OS I am on (macOS / Windows / Linux) only if you need it for paths.
Do not install an emulator in this step — that is a separate task.
```

### 4. Install & run emulator

Use this when the project exists but you still need a place to launch the app.

```text
I need a working mobile emulator/simulator so I can run my Expo (React Native)
app during a workshop.

Context:
- OS: [macOS / Windows / Linux]
- Chip: [Apple Silicon / Intel / other]
- Goal: open the current project on an emulator with the fewest steps
- Prefer: [Android emulator / iOS Simulator / whichever is fastest on this machine]

Work evidence-first. Do the following:

1. Detect what is already installed (Android Studio, SDK, emulator images,
   Xcode, simulators, Expo CLI / npx, Java). Report what you find.
2. Propose the shortest path to ONE working target (don’t set up both
   Android and iOS unless I ask).
3. Give me copy-paste commands (or precise GUI clicks) to:
   - install only what is missing
   - create or select one AVD / simulator
   - boot it
   - start the Expo app against that target
4. If something fails, ask for the exact terminal error before guessing.
5. End with a “verify” checklist: 3 commands or clicks that prove the
   emulator is up and the app bundle is loading.

Constraints:
- Prefer free official tooling (Android Studio / Xcode).
- Do not require a physical device.
- Do not change product scope or rewrite the app — environment only.
- Warn me about disk space / download size before large installs.
```

### 5. First mobile screen + flow

```text
Implement only the approved mobile scope below — nothing else.

Scope:
- User: […]
- Version 1 action: […]
- Visible result: […]
- Done when: […]

Build order:
1. Primary screen UI (clear hierarchy, large tap targets, portrait phone).
2. Wire the Version 1 action with sample/local data (no real backend unless
   already agreed).
3. Show the Visible result on screen after the action.
4. Add a minimal empty or error state if the happy path can fail.
5. Tell me how to verify Done when on the emulator in under 60 seconds.

Rules:
- Do not add auth, payments, push notifications, or extra tabs.
- Prefer editing existing files over new abstractions.
- After changes, list exact files touched and the verify steps.
```

---

## Quick verify (before you call a mentor)

- [ ] Emulator/simulator window is visible and unlocked  
- [ ] `npx expo start` (or your stack’s start command) is running without red errors  
- [ ] App opens and shows your primary screen  
- [ ] You can complete Version 1 action → Visible result once  
- [ ] You can narrate problem → what you built → what’s next in ≤90 seconds  

If expected ≠ actual, paste evidence into [Unstuck](/prompts/unstuck).

---

## After the practical

- Optional: skim [RevenueCat docs](https://www.revenuecat.com/docs) only if the core flow works and you still have time  
- Shipaton submission / store release is **after** the room sprint — see the event pack  
- Keep shipping with [Quality gate](/prompts/quality-gate) before any wider demo
