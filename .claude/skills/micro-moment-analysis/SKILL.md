---
name: micro-moment-analysis
description: Run a micro-moment marketing analysis on a final persona list: find the exact real-world moments a persona's problem fires (year/week/day), why they care and what drives it, how customers describe it in reviews, what tipped them to buy now, and which moments people share on social. Produces an MD working database plus a readable HTML report per persona. Use when the user asks for a micro moment analysis, trigger moments, "why now" research, review language mining, or social comparison research for ad creative on personas, even if they don't name the method.
---

# Micro-Moment Analysis

Run a micro-moment analysis for a marketing agency client, following the method below.

---

## 1. What this analysis is and where it sits

The research pipeline this analysis belongs to:

1. Review the client's reviews and current ads → long list of personas (plus personas added from intuition).
2. Pick the target generation → shorter persona list.
3. Generational insights research → final persona list.
4. **Micro-moment analysis (this file)** → how to talk to each final persona: when their problem fires, why they care, and how they describe it.

Generational research tells you someone's worldview. It does not tell you *which moment* the product becomes relevant to them. This analysis fills that gap.

**Core principle.** A good strategist finds pain points. A great strategist finds **when** those pain points show up and **why**: the exact moment in the year, week and day that the "I have a problem" thought fires. Real-world situations, not marketing situations.

- Weak: "She wants to lose weight." Obvious, and every competitor already knows it.
- Strong: "She's getting dressed for lunch with a friend who just lost a lot of weight. Her jeans won't zip. She's anxious before she even leaves the house."

**Why hyper-specific.** Meta's Andromeda update is interest-based and rewards hyper-specific content. A hyper-specific situation gives the creative team something to write toward, somewhere to put the camera, a creator to cast and a story to tell.

Emotional mapping is a **separate** analysis. Do not do it here and do not shape outputs around it.

---

## 2. The four tasks

These are four separate tasks with four separate outputs, not steps toward one goal. They reference each other through IDs (section 4.1).

| Task | Name | Tier | Main sources | Answers |
|---|---|---|---|---|
| T1 | Trigger moments & daily friction | **Basics, mandatory** | Reddit, Facebook Groups, niche forums | When does the problem fire, why does she care, what drives it? |
| T2 | Emotional language around the problem | **Basics, mandatory** | Client's Amazon reviews (5★, 3★, 1★), Trustpilot | In what words does she describe it? What to promise, what objections to address? |
| T3 | Why now (unfiltered customer voice) | Strategist fuel | Owned data (surveys, quiz data, CS tickets, post-purchase surveys); public fallback | What tipped her from "I should" to "I'm buying today"? |
| T4 | Social comparison moments | Strategist fuel | TikTok / Instagram comments on related content | Which moments are emotionally strong enough that people share them? |

**How to treat the tiers.** The strategist (Vojtech) talks about T1 and T2 as "just the basics". Do not read that as "less important". T1 and T2 are used for about 99% of ads and must be done extremely well, every time. T3 and T4 are where breakthrough ("one ad in a million") ideas come from, and they build on T1 and T2. T4 is a variation of T3.

**Where the output stops.** T3 and T4 stop at **ranked evidence**. Do not write hooks, ad concepts or scripts for them. Vojtech does the creative jump from there.

---

## 3. Step 0: Setup

### 3.1 Inputs to get from the user
- The final persona list, with descriptions. **Run one persona fully through all four tasks first**, then scale to the others.
- Client and product.
- The client's review pages (Amazon, Trustpilot links).
- Owned data, if it exists (surveys, quiz data, CS tickets, post-purchase surveys).
- Any moments already supplied with the persona description.

If something is missing, ask for it before starting.

### 3.2 Access check
Before researching, test which sources are actually reachable from this environment: Reddit, Facebook Groups, forums, Amazon, Trustpilot, TikTok, Instagram. Tell the user which ones need them to supply exports or screenshots. Do this on day one, not mid-task.

### 3.3 File setup
Every analysis produces two files for the persona being run (e.g. `analysis/<client>/<persona-code>.md` and `.html`):

- **MD file: Claude's working database.** All cards, fields, evidence, links, scores and status. Update it as you work.
- **HTML file: the readable version for Vojtech.** Vojtech cannot practically read MD, so everything they need to review must be in the HTML. IDs are clickable links that jump to the referenced card. Summaries come first, then cards.

Assign a short persona code (e.g. `W57` for a 57-year-old woman).

Build the HTML from `assets/report-template.html` (in this skill's folder). It already has the layout, styles, section order and card patterns. Copy it, fill the placeholders, and repeat the card blocks as needed. Keep every card `id` attribute equal to its ID so `href="#W57-T1-03"` links work. Regenerate the HTML from the MD whenever the MD changes meaningfully, and send it to the user (SendUserFile, display "render") at each checkpoint and at the end.

---

## 4. Shared rules (apply to all tasks)

### 4.1 IDs
Format: `[PERSONA]-[TASK]-[NN]`, e.g. `W57-T1-03` = persona W57, Task 1, item 3. Chains add a letter: `W57-T1-03a`. Drivers add `-D#`: `W57-T1-03a-D2`. Every cross-reference uses IDs, and in the HTML every ID is a link.

### 4.2 Evidence
- Quotes are **verbatim**: exact wording, typos included, with source link and date. Paraphrases only go in "notes" or "ad use" fields.
- Never invent quotes, sources or counts. Anything inferred or reasoned rather than found is labelled **hypothesis**.
- Frequencies are **counted**, not estimated.

### 4.3 Saturation
Stop collecting for a task when new sources only repeat what is already found. The target volumes in each task are a sanity check, not the stopping rule.

### 4.4 The emotional chain
Every moment is not just a *what*. Mediocre research finds the moment and stops. Each moment needs a chain explaining why the person cares and what is behind that:

| Layer | Question | Example |
|---|---|---|
| **What** (the moment) | What is physically happening? | Her jeans won't zip before lunch with a friend |
| **Catalyst** (often, not always) | What intermediary makes the moment hurt right now? | The friend just lost weight |
| **Why she cares** | What is the surface emotion? | She feels insecure / embarrassed |
| **Driver** | What specifically is behind the caring? | She'll look fat next to her friend; others will see the contrast and laugh |

- The same *what* with a different catalyst is a different chain, and a different ad. Friend lost weight → "I'll look fat next to her". Friend is pretty → "I'll be invisible". Friend is rich → "fitness was the one thing I had on her". No catalyst → "my body isn't mine since menopause".
- The persona description usually makes the right chain obvious. Expect **one chain per moment**, two only when the persona genuinely leaves it open.
- When there is no catalyst, go straight from the what to the why.

### 4.5 Driver discovery: whatever is still unclear
The driver layer is not a fixed field. It answers whatever is still unclear after "why she cares".

1. **Read "why she cares" and ask: does it already explain the motivator?**
   - If not, answer that gap first.
   - If it does, move to the next open question: in what specific scenario does it hit, and why does that bother her? E.g. "friend lost weight, so she feels insecure" already explains that she feels fat. So the next question is why feeling fat bothers her.
2. **List driver hypotheses**, both from the data and from reasoning beyond it. E.g. others will see the contrast and laugh; the friend will judge her; it'll show up in photos; it signals she's undisciplined, which is a mark on her name (more common in men).
3. **Validate against the data.** Two possible outcomes:
   - **A.** The hypotheses are confirmed. Either one driver wins on both volume and intensity, or they split, e.g. D1 leads on volume but D3 is the most intense.
   - **B.** The data shows drivers not yet considered. Add them and rank them too.
4. **Rank on two axes and keep both:**
   - **Volume (quantity):** how many people it drives.
   - **Intensity (quality):** how hard it hits.

   A 35% driver and a 30% driver let you reach the most people. A 10% driver with very high intensity is where the quality ads come from. Report volume leaders, intensity leaders, and any driver strong on both.
5. **Label confidence honestly.** It will usually be somewhat vague. Unconfirmed hypotheses stay in the table marked "unconfirmed"; do not delete them.

**Driver table fields:** driver ID, hypothesis, origin (data / reasoning / new from validation), status (confirmed / new / unconfirmed), volume (share or count), intensity (score), evidence (quotes + links), confidence.

### 4.6 Depth: three whys, then a checkpoint
1. By default, ask "why" **three times** per chain.
2. Then **stop and check with the user** using the AskUserQuestion pop-up. Show the what and the three whys. Batch up to 4 chains per pop-up, one question per chain, most important chains first. Options per chain:
   - **Stop here.** This depth is right.
   - **Do one more.**
   - **Do X more.** The user types the number via "Other".
3. Continue until the user picks "stop here" for each chain.

**How to read depth when presenting it.** Each level of "why" moves the emotion further outward:

| Level | Where the emotion lives | Example | Can an ad show it? | Role |
|---|---|---|---|---|
| Internal | In her head | "She feels insecure" | Hard, it's invisible | Context only |
| **Visible** | Out in the world, involves the other person | "She'll look fat next to her friend" | Yes: show it, joke about it, exaggerate it | **Headline driver.** The main selling point to the client and in the campaign. Deep enough for about 90% of people |
| **Social** | Other people watching | "Others will see the contrast and laugh" | Yes | **Supporting layer.** The final nail in the coffin, not the headline |
| Too deep | Abstract or existential | "Afraid of losing her place in her social circle" | Awkward, too heavy for most people | Note it, don't lead with it |

Each chain gets a short **depth verdict** naming its headline driver and its supporting layer.

### 4.7 Intensity scoring
Score intensity on **three signals**:
- **Language strength:** how strongly it's worded.
- **Behaviour change:** whether the moment changes what they do (cancel, hide, avoid, buy).
- **Engagement:** tags, replies, upvotes, likes.

Which signal matters most depends on the data. So the **weights are set for each analysis** once the nature of the data is visible (Final assembly, section 9). Examples: mostly reviews → language-heavy (e.g. 60/25/15); mostly TikTok comments → engagement-heavy; mostly Reddit stories → behaviour-heavy. Any split is allowed (e.g. 90/10/0, 30/30/40). Record the weights used and one line on why.

Until weights are set, store the three raw signal scores (1–5 each) separately.

---

## 5. Task 1: Trigger moments & daily friction (basics)

**Goal.** For the persona, 3–5 real, first-person, timed situations where "I have a problem" fires. Each has an emotional chain and ranked drivers, specific enough to brief as an ad scene without inventing anything.

### Procedure
1. **Search wide.** Look through Reddit, Facebook Groups and niche forums using persona-specific angles: life stage, situations, words they'd use. Look for first-person stories ("I was at the dentist and…", "I was shopping with my niece…"). Expect to see many candidate moments (roughly 15–25).
2. **Select 3–5.** Start with **3**. Expand to **5** only if the data shows more are worth keeping.
   - Moments supplied with the persona description count toward the 3. If only 1–2 are supplied, still explore for the others.
   - Pick using the persona description plus the data: specificity, frequency, and fit.
3. **Build the chain** for each selected moment (section 4.4).
4. **Ask "why" three times**, then run the **checkpoint** (section 4.6).
5. **Discover drivers** (section 4.5): hypotheses, validation, then a first volume score and language-strength score.
6. **Mark driver rankings provisional.** T2 adds volume and language signals, and T4 adds engagement. Final ranking happens in section 9.

### Moment card fields
- `id`, `persona`, `title` (scene name, up to 8 words, e.g. "Jeans won't zip before friend lunch")
- `situation`: 2–3 sentences on what is physically happening
- `timing_year` / `timing_week` / `timing_day`: from evidence, otherwise "unknown"
- `setting`, `others_present` (or who they are thinking about)
- `friction_type`: physical / social / practical / identity
- `immediate_reaction`: what they do in the moment
- `verbatim_quotes` (1–3), `sources` (links, platform, date, count of independent mentions)
- `why_selected`: one line
- `chains`: catalyst, why she cares, the whys, depth verdict, driver table
- `specificity_score` (1–5, 5 = filmable as-is), `frequency_signal` (low / med / high)

### Quality bar: a card passes only if
- A camera could film it: real place, time and action.
- It names a trigger event, not a goal ("jeans won't zip", not "wants to lose weight").
- It has at least one real first-person quote with a link.
- At least one timing field comes from evidence.
- It is a real-life situation, not a marketing one.

### Summary in the output
- The selected moments, with why each was chosen.
- An **"Also seen"** list of runners-up (one line each), so the user can swap one in.
- Timing pattern: when the problem fires most.
- Gaps: anything resting on a single source.

---

## 6. Task 2: Emotional language around the problem (basics)

**Goal.** The customer's own words for each layer of the T1 chains, plus what to promise (5★), the objections to address (1★), and where they hesitate (3★).

**Scope.** Client reviews **only**. Competitors are offered at the end (section 9).

### Procedure
1. **Collect** the client's reviews in three bands: 5★, 3★ and 1★. Use Trustpilot too if available.
2. **Tag each quote:**
   - Type: before-state / after-state / tipping point ("what finally made me buy") / wish I'd known / promise / objection / 3★ hesitation.
   - Primary emotion.
   - `chain_link`: which T1 moment, chain **and layer** it belongs to (what / why she cares / driver).
   - `driver_vote`: whether it supports an existing driver or suggests a new one.
   - Persona fit (strong / partial), with the cue it's based on.
3. **Count** the frequency of each theme. This feeds driver **volume**.
4. **Score language strength** (1–5). This feeds driver **intensity**.
5. **Objections.** Pair each with one line that addresses it. Objections do **not** get a why-chain.
6. **Compare 5★, 3★ and 1★** to find objections (per the mentor: the differences between the bands reveal objections).
7. **Feed back to T1.** Update driver volume and language scores. New drivers or moments go back through T1 (sections 4.4–4.6). The total of selected moments stays at 5 or fewer: flag anything stronger rather than silently adding it.

### Language card fields
`id`, verbatim quote, type, star rating + source + link + date, emotion, persona fit, `chain_link`, `driver_vote`, frequency, severity (objections only, 1–3), ad use (draft line).

### Quality bar
- 100% verbatim.
- Emotional, not functional ("I hid in photos", not "lost 5kg").
- Each quote names a situation or feeling, not just a claim about the product.
- Every objection has a line that addresses it.
- Frequencies are counted.

### Summary in the output
- Top promises (from 5★), ranked by frequency × intensity.
- Top objections (from 1★), each with its addressing line.
- 3★ hesitation themes: "it works, but…".
- A list of 10–15 phrases to use word for word.
- A list of words to avoid (words customers reject or find clinical or patronising).
- The top 3 "what finally made me buy" reasons.

**Target volume:** about 40–60 cards, subject to saturation.

---

## 7. Task 3: Why now (strategist fuel)

**Goal.** The events that turned "this keeps happening" into "I'm buying today". The T1 moment is when the *problem* fires, which can happen many times. T3 finds when *buying* fires. The gap between the two is the insight.

### Procedure
1. **Source.** Use owned data if it exists. If it doesn't, **run anyway** on public reviews and posts with timing language ("finally bought it after…", "the day I…", "that was the last straw"), and mark those entries lower confidence.
2. **Extract for each entry:**
   - Tipping event (who, where, what).
   - **Last straw vs. enabling condition**, kept separate. The last straw is the emotional push. The enabling condition is what made buying possible: payday, a discount, proof from someone they know, time alone.
   - Consideration span: how long they'd been thinking about it.
   - The objection they had → what overcame it.
   - Timing marker, with at least two levels (e.g. season + day).
   - Verbatim quote.
   - Source type: owned / public.
   - Confidence: high (owned, explicit) / med (public, explicit timing) / low (inferred).
3. **Link** each entry to the T1 chain it resolves, or flag it as a new trigger. New triggers go back to T1.
4. **Cluster** entries into 3–6 why-now patterns and rank them. A pattern resting only on low-confidence entries is labelled a **hypothesis**.
5. **Stop at evidence.** No hooks or ad concepts.

### Summary in the output
- The ranked why-now patterns, each with frequency, average confidence and supporting entries.
- **Wildcard:** the single strangest tipping event you're confident in.

**Target volume:** at least 15 entries, subject to saturation.

---

## 8. Task 4: Social comparison moments (strategist fuel)

**Goal.** Public proof of which moments are emotionally strong enough that people share them, plus what the whole category is already sensitive to. If people tag friends in a moment, it has creative energy.

### Procedure
1. **Search at category level** (how people think about the category as a whole, e.g. weight-loss supplements, beef snacks, streetwear, dog leashes). Look at TikTok and Instagram comments on related organic content, especially posts with lots of "tag a friend" and "this is SO me" comments. Use whatever access route the access check (3.2) confirmed.
2. **Capture each moment card:**
   - Source post (platform, creator type, format, link, date) and its hook, verbatim.
   - The moment depicted.
   - **Comparison axis:** who they compare themselves to (friend, younger self, partner, sister…). This usually maps to a T1 catalyst.
   - Share behaviour: tag / "so me" / stitch / save / argue.
   - Who tags whom (relationship).
   - 3–5 verbatim comments.
   - Engagement signal: tag count, "so me" count, total comments, share of comments that are tags. This feeds intensity.
   - Sentiment.
   - Sensitivity flag: the nerve it hits, plus any landmines.
3. **Tag personas.** Rank at **category level**, but attach the persona(s) each moment speaks to (it can be several). Persona tags are for reference only and do not affect the ranking. If a high-energy moment fits **none** of the personas, flag it: it may point to a persona that was cut too early.
4. **Validate T1–T3.** Mark each T1–T3 moment and chain as **confirmed / weak / contradicted**. Note which catalysts people relate to most.
5. **Loop back.** New moments go back to T1 for the full treatment, including the user checkpoint. If one beats a selected moment, flag it rather than silently adding it.
6. **Stop at evidence.** No hooks or ad concepts.

### Summary in the output
- **Category snapshot:** 5–8 bullets on how people talk about the category, recurring jokes, sore spots, words that cause backlash, what feels "salesy". This is the "don't touch" layer that applies to every persona.
- Moments ranked by creative energy (category level), with persona tags.
- A validation matrix for the T1–T3 moments.

**Target volume:** about 8–15 cards from at least 2 platforms, subject to saturation.

---

## 9. Final assembly

1. **Set the intensity weights.** Look at the nature of the data collected and propose the language / behaviour / engagement split with one line of reasoning. Confirm it with the user.
2. **Final driver ranking** for each chain: volume leaders, intensity leaders, any driver strong on both, and the depth verdict (headline driver vs. supporting layer).
3. **Finalise the files.** Complete the MD database and the HTML. The HTML order is:
   - Overview: persona, the selected moments, and the headline driver for each.
   - T1, then T2, T3, T4.
   - Every ID is a clickable link.
4. **Offer competitors.** Ask: "This was done on the client's reviews. Do you want it rerun on a mix of the client's and competitors' reviews?"
5. **Scale.** After the first persona is reviewed, run the remaining personas the same way.

---

## 10. Working with Vojtech
- Vojtech often talks about the basics (T1, T2) as if they don't matter. That's their style ("AD carry method"): they want the basics delivered extremely well so they can push past them. Never cut corners on the basics because of how they're described.
- Vojtech does the creative work. Deliver evidence and rankings, not finished ads, especially for T3 and T4.
- Vojtech reads the HTML, not the MD. Anything they need to see or decide goes in the HTML or in a pop-up.
- Use pop-ups (AskUserQuestion) for decisions, with concrete options.
