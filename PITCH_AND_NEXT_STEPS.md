# EasySign Care — Pitch Plan & Next Steps

Hackathon: EuroTech Hong Kong Hackathon — Munich 2026 (HealthTech track)

**Deliverables:** GitHub repo · 2-min business video · 2-min technical video · 2-min live pitch (judges watch videos first)

**Scoring (HealthTech track):** Innovation (20) · Impact & Scalability (20) · Feasibility (15) · Hong Kong Alignment (15) · Presentation (10)

**Judge questions to answer:** Who pays? What breaks at scale?

---

## One-line positioning (use everywhere)

> **EasySign Care is a real-time visual communication bridge between hospital staff and deaf patients — until a sign language interpreter arrives.**

---

## Verdict: is the current build enough?

**Yes — for a strong hackathon demo**, if the pitch is sharp and submission is honest.

You are **not** in crowded buckets (symptom checker, mental wellness, TCM bot). You address a real gap:

> **Hospital staff ↔ deaf/HoH patient communication when no sign-language interpreter is in the room.**

### What judges can see working today

- Staff speaks/types → patient sees **sign animation** (visual-first; no audio on patient kiosk)
- **Dual-screen live visit** (`/care/staff` + `/care/patient`, synced via room code)
- **Preset clinical phrases** + **custom voice recording**
- **Patient → staff gestures** with triage alerts (e.g. closed fist = emergency)
- **Cantonese** input in main EasySign app (HK localization story)

### What not to claim

- Direct Cantonese → Hong Kong Sign Language (HKSL) if the pipeline is English-mediated internally
- Full EHR / FHIR integration unless actually built
- Replacing certified sign language interpreters (position as **bridge until they arrive**)

**Rule:** One killer live flow beats five half-built features. The dual-screen demo is the strongest asset.

---

## Video vs live pitch — division of labour

Judges watch videos **before** the live pitch. Do not repeat the same content in all three.

| Asset | Purpose | Tone |
|-------|---------|------|
| Business video | Problem, market, HK angle, who pays | Emotional, accessible |
| Technical video | Architecture, what’s real, honesty | Engineer-to-engineer |
| Live pitch | One unforgettable demo + why now | Confident, rehearsed |

---

## 2-minute business video

### Structure

| Time | Content |
|------|---------|
| 0–15s | **Hook:** *"A deaf patient arrives at A&E. The nurse speaks. Nothing reaches them."* |
| 15–45s | **Problem:** communication gap, interpreter wait times, written notes ≠ sign language |
| 45–75s | **Solution:** EasySign Care — visual sign bridge until interpreter arrives |
| 75–105s | **Business:** who pays, staff efficiency, patient safety |
| 105–120s | **Hong Kong:** Cantonese input, bilingual subtitles, HA / deaf community NGOs, GBA expansion |

### Show on screen

- Split-screen or screen recording: staff taps phrase → patient sees animation
- No deep technical detail

### Answer “who pays?”

- Hospital ops / patient experience budgets
- NGOs and care homes serving deaf/HoH communities
- Reduces risk and staff friction while interpreter is en route

### Answer “what breaks at scale?”

- Sign language variety (be honest: English-mediated bridge today; HKSL-native path on roadmap)
- You are the **triage communication layer**, not a replacement for certified interpreters

---

## 2-minute technical video

### Structure

| Time | Content |
|------|---------|
| 0–20s | Architecture: speech/text → STT / translation → SignWriting + pose animation |
| 20–50s | **Live visit sync:** `/care/staff` ↔ `/care/patient`, BroadcastChannel + room ID |
| 50–80s | **Staff:** phrase board + custom voice → pipeline → patient kiosk (animation only, no TTS) |
| 80–100s | **Patient:** MediaPipe gesture pack → triage overlay on staff console |
| 100–120s | What’s real vs mocked · point to `HONESTY.md` in repo |

### Show on screen

- Real screen recording: room code, phrase tap, custom voice record, closed fist → red staff alert

### Say on camera (honesty)

> *"Sign animation uses our English-mediated pipeline today. Cantonese is localized at the speech layer. HKSL-native generation is on our roadmap."*

---

## 2-minute live pitch

Videos explain *what* — live pitch is *why you, why now, one live moment*.

### Suggested flow

1. **10s** — One-sentence problem + one-sentence solution
2. **20s** — HK angle: *"Built for Hong Kong's bilingual hospitals and deaf community — Cantonese in, visual signs out."*
3. **70s** — **Live dual-screen demo** (windows pre-opened, same room code):
   - Staff records: *"Please wait, the doctor will see you soon"*
   - Patient screen updates (animation, silent)
   - Patient: closed fist → staff critical overlay
   - Staff taps a preset phrase
4. **20s** — Impact + close: bridge until interpreter; visit log for handoff; path to HA pilots

### Do not

- Walk through every feature
- Rely on audio on the patient side
- Overclaim HKSL or EHR integration

---

## How the build maps to judging criteria

| Criterion | Current strength | Strengthen with |
|-----------|------------------|-------------------|
| Innovation (20) | Dual-screen care mode + gesture triage | "Bridge layer" vs generic translation apps |
| Impact (20) | Patient safety, dignity, staff efficiency | Visit summary + interpreter handoff story |
| Feasibility (15) | Working demo, real APIs | `HONESTY.md`, rehearsed stable flow |
| HK alignment (15) | Cantonese mode in main app | Cantonese in Care staff + HK orgs in business video |
| Presentation (10) | Dual-screen is memorable | Rehearse window layout; silent patient screen |

---

## Missing features — priority list

| Priority | Item | Why | Effort |
|----------|------|-----|--------|
| **Must** | `HONESTY.md` in `easysign/` | Track doc: missing it can **disqualify** | ~30 min |
| **Must** | Clear HK slide in business video | 15 pts on HK alignment | Writing only |
| **High** | Visit summary export (copy / PDF of visit log) | Answers "what happens after?" + interpreter handoff | ~2–3 hrs |
| **High** | Cantonese staff recording in Care | Reuses existing API; strong HK wedge | ~2 hrs |
| **Medium** | Scenario presets (A&E / ward / discharge) | Domain depth without new screens | ~1 hr |
| **Skip now** | FHIR, EHR, WebSocket two-laptop sync | High effort, low 2-min demo payoff | — |

**Recommendation before submission:** Do not chase big features. If you have 2–4 hours, only add `HONESTY.md`, visit summary export, and Cantonese record in Care.

---

## Next steps (action checklist)

### Submission (mandatory)

- [x] Create and commit `easysign/HONESTY.md` (what is real vs mocked; no secrets in repo)
- [ ] Verify `.env` is gitignored; only `.env.example` in repo
- [ ] GitHub repo clean README + link to EasySign Care routes
- [ ] Record 2-min business video
- [ ] Record 2-min technical video
- [ ] Rehearse 2-min live pitch (timed)

### Product (high-value, optional)

- [ ] Visit summary — "Copy visit log" on staff console
- [ ] Cantonese toggle on staff custom message (record Cantonese → translate → signs)
- [ ] Scenario filter on phrase board (A&E / ward / discharge)

### Demo rehearsal

- [ ] Backend running; API keys set
- [ ] Two windows: staff left, patient right, **same room code**
- [ ] Patient side: no TTS / volume irrelevant
- [ ] Test path: custom voice → phrase tap → closed fist gesture
- [ ] Pre-record backup clip if live gesture fails on stage

### Pitch materials

- [ ] One-slide architecture diagram for technical video
- [ ] One-slide HK market slide (HA, deaf NGOs, Cantonese, GBA)
- [ ] One-slide business model (who pays)
- [ ] Memorize one-line positioning

---

## Demo script (70 seconds live)

1. Open **EasySign Care** → **Open staff console** + **Open patient screen** (split screen).
2. Staff: **Record** → *"The doctor will come soon."* → patient animation plays (silent).
3. Patient: hold **closed fist** → staff **Critical** overlay + visit log entry.
4. Staff: **Acknowledge** → tap preset *"Do you have any pain?"*
5. Close: *"This is the bridge until a certified interpreter arrives — with a visit log they can read in 30 seconds."*

---

## Hong Kong angle (for business video & live pitch)

- Bilingual hospitals (Cantonese + English) — staff can speak either; patient sees visual signs
- Hospital Authority serves diverse patients including deaf/HoH communities
- Interpreter scarcity in peak hours (A&E, ward rounds) — EasySign Care fills the gap
- Expandable to care homes, NGOs, GBA cross-border care settings
- Does **not** require claiming to be native HKSL — honest localization layer story

---

## Architecture (for technical video)

```text
Staff console (/care/staff)
  ├── Preset phrases / custom voice (STT)
  ├── Sign pipeline: text → SignWriting + pose animation
  └── BroadcastChannel → Patient kiosk

Patient kiosk (/care/patient)
  ├── Receives phrase → shows text + sign animation (no audio)
  └── Camera → gesture pack → triage alert → Staff console

Main EasySign (/)
  └── General speech/text → signs (English + Cantonese modes) — unchanged
```

---

## Files & routes reference

| Route | Role |
|-------|------|
| `/` | Main EasySign (translate, SignWriting, animation) |
| `/care` | Start live visit launcher |
| `/care/staff?room=XXXX` | Staff console |
| `/care/patient?room=XXXX` | Patient kiosk |

---

*Last updated: June 2026 — EuroTech Hong Kong Hackathon, HealthTech track*
