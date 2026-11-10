# Attending Rounds

**Clinical reasoning practice for medical school and clerkships.** A static, offline-capable web dashboard with no required account, API keys, backend or paid service.

## What's included

- **108 original patient cases and 648 questions (including the original 27 cases, plus 81 new cases)** across 9 specialties: Family Medicine, Internal Medicine (Outpatient), Internal Medicine (Inpatient), Pediatrics, General Surgery, Surgical Specialties, OB/GYN, Psychiatry and Anesthesia.
- Six stages per case: clinical recognition, investigations, pathophysiology, management, complications and an advanced attending challenge.
- **Free response and multiple choice**, selectable globally or switched within **any currently unanswered question**. The **Go multiple choice** button shows four options immediately, without restarting or losing typed work. You may switch back prior to answering.
- Multiple-choice scoring is instant; open response offers a model answer and **transparent self-grading** (fully correct, partially correct, missed). This application does **not** claim to evaluate nuanced clinical prose with AI.
- Three session modes: **Attending Rounds** (adaptive follow-up prompts plus simulated management-response branches), **Full Patient Case** (linear stages), and **Rapid-Fire** (10 questions selected from cases).
- Optional cues, additional attending probes, review queue, debrief, case-by-case performance and specialty analytics.
- A **reference link on every case**: direct clinical/professional guidance where specifically checked and an explicitly labeled NCBI Bookshelf **topic-search** link elsewhere. A topic-search link is **not** a claim that the individual case or all its decisions have been independently fact-checked. Always verify current guidance and local protocols.
- Custom case builder, bulk import from structured JSON, backup import/export.
- No network data collection or remote database. All history and custom cases persist in your browser's `localStorage` for that site origin.

## Expanded case library and scope

- Exactly **12 distinct cases in each of 9 specialties**, covering routine presentations and high-acuity/advanced scenarios.
- **Case difficulty** is selectable on the dashboard and filterable in the library: **20 Foundations**, **48 Clinical**, **40 Advanced**. This is a separate setting from the question-depth setting: every case still progresses through six stages.
- The original 27 case IDs and question IDs are unchanged. Existing browser progress and study backups remain compatible when upgrading the same GitHub Pages deployment.
- All questions and case stories are original study content, not copied from clinical case books or institutional exam question banks. Multiple-choice diagnosis choices include three authored clinical near-misses; mechanism, treatment, investigation, complication, and nuance distractors are selected from other medically meaningful options within the same rotation. Some will be more challenging than others.
- **Content caveat:** this is an educational practice collection, not an independently clinician-reviewed question bank. Guideline updates and individualized clinical management may change the preferred answer.

## Open it now

**Easiest**: Open `Attending_Rounds_Standalone.html` in a modern browser. It includes the styles, built-in case bank and application code in one file.

**Project version**: Open `index.html` with `styles.css`, `cases.js`, and `app.js` in the same directory. For the most consistent saved-progress behavior, host on a static HTTPS site such as GitHub Pages.

## Publish with GitHub Pages

1. Create a new GitHub repository (e.g. `attending-rounds`).
2. Upload `index.html`, `styles.css`, `cases.js`, `app.js` to the **root directory**. The other files are optional, but `cases.json` is convenient for future editing.
3. In GitHub **Settings → Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Visit `https://YOUR-USERNAME.github.io/attending-rounds/` once GitHub indicates deployment is complete.
5. Bookmark the link on your computer or phone.

The GitHub Pages URL is an example pattern, not a live link created for you. Hosting the files does **not** synchronize practice progress: `localStorage` is per browser and origin. Use **Export study backup → Import study backup** to move data between devices.

## Usage notes

### Free response and MC fallback

1. Choose **Free response** in Overview or Settings and start a case.
2. Type your reasoning in the question's text area.
3. To make it easier, choose **Go multiple choice**. Four responses appear for the **same question**. The typed response is retained if you return to free response.
4. Clicking an option immediately marks it correct/incorrect and shows the correct response and rationale. A switch to multiple choice or use of a requested hint applies **80% credit** to an otherwise correct result, marking it as assisted learning. The supportive attending and foundations level can show guiding hints by default without manually requesting a hint.
5. In free response, choose **Check my response**. The model answer is revealed and you evaluate your answer as correct / partial / missed.
6. **I don't know** reveals the answer and counts the question as missed. **Hint** shows a guiding clue first.

### Modes and difficulty

- **Attending Rounds**: Your response can determine whether a patient stabilizes or deteriorates in the later stage. Incorrect/partial answers may prompt an additional teaching probe.
- **Full Patient Case**: A predictable, linear six-stage progression.
- **Rapid-Fire**: A selected set of 10 single-question challenges. A missed-question review queue is also available.
- **Case difficulty selector**: Foundations, Clinical, Advanced, or All difficulties; restricts random case selection and Rapid-Fire pools.
- **Questioning depth selector**: Foundations provides guiding hints, Clinical is the default, and Attending increases follow-up probing; it does not restrict the case bank.
- **Attending style**: Supportive shows cues, Standard uses normal hints, Challenging emphasizes follow-up probing.
- **Feedback style**: Immediate prioritizes reviewing the answer, Hybrid offers additional clarification, Realistic may ask a deeper question before showing the model answer if the question contains an authored probe.

### Add cases

- In **Add Cases**, complete a presentation and all six questions with a correct answer, three MC distractors, explanation and optional hint.
- To import multiple cases, use **Download case JSON template**, edit the data, then choose the JSON file with **Import cases**.
- A `cases.json` reference library is included in this archive. The code also includes `expand_bank.py` for editing or rebuilding the 81 additional cases from the preserved original 27-case base.

## Research references

The new cases were informed by web review of authoritative topic material, including AAFP primary care guidance, professional Merck Manual topics, AAP pediatric guidance, ACOG obstetric bulletins, CDC STI treatment guidance, ASRA anesthesia safety materials, AHA/ACC cardiovascular guidelines, and APA psychiatric guidance. Selected cases have direct verified links in the app. Others deliberately link to an **NCBI Bookshelf search** as a starting point for further reading rather than implying a specific guideline endorsement. Guidelines may be paywalled or superseded; check publication dates.

## Important limitations

This is a **rule-based, curated educational simulator**, not a live patient simulator with a generative AI clinical reasoning model. Branches are predetermined by whether a management question was graded correct or not, and follow-up probes are authored. It does not autonomously generate cases from PDFs or slide decks and does not accurately grade free-text medicine answers. These capabilities need additional services and safeguards.

Clinical content is a learning aid only. Clinical guidelines, especially dosing and obstetric/pediatric/emergency pathways, change. Review the linked primary sources, up-to-date institutional guidelines, and attending supervision before using information for patient care. Do not enter protected health information or real patient identifiers into custom cases.

## Files

- `index.html`: multi-file app entry page
- `styles.css`: responsive visual design
- `cases.js`: built-in patient case bank loaded by browser
- `app.js`: interactive controls, session progression, scoring, history and importer
- `cases.json`: editable JSON copy of the included case bank
- `Attending_Rounds_Standalone.html`: everything embedded in a single HTML file
- `README.md`: instructions and constraints
- `expand_bank.py` + `base_cases_v1.json`: original supplemental case authoring source and preserved baseline (optional for web deployment)
