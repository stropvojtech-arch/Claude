# Session context: Micro-Moment Analysis skill

Paste this into a new session to continue where we left off. Vojtech is the strategist (they/them).

---

## 1. What we're doing
We turned Vojtech's research mentor's Zoom transcript on **micro-moment analysis** into a repeatable method for Claude, and then into a **skill** called `micro-moment-analysis`.

**Status:** the method is designed, written and packaged as a skill. It has **not** been run on a real persona yet. The next step is the first real run.

**Where the skill lives:**
- GitHub `stropvojtech-arch/Claude`, branch `claude/gracious-hopper-2w5r8u`, path `.claude/skills/micro-moment-analysis/`
  - `SKILL.md`: the full method
  - `assets/report-template.html`: the layout for the HTML report Vojtech reads
- Vojtech wants it in `~/Desktop/Claude/.claude/skills/micro-moment-analysis/` on their computer. If it isn't there yet, copy it from the branch above.
- Note: that GitHub repo is **public**.

Stages of the project:
1. Break the transcript into parts ✅
2. Define each task's output ✅
3. Plan how to reach each output ✅
4. Write the instructions as MD ✅
5. Turn them into a skill ✅
6. **First real run on one persona ⏭️ next**

---

## 2. Where this analysis sits in Vojtech's research process
1. Review the client's reviews and current ads → long list of personas (plus personas added from intuition).
2. Pick the target generation → shorter list.
3. Generational insights research → **final persona list**.
4. **Micro-moment analysis** → how to talk to each persona: when their problem fires, why they care, how they describe it.

Generational research gives someone's worldview, but not the *moment* the product becomes relevant. Micro moments fill that gap.

**Emotional mapping** comes up at the very end of the mentor's transcript, but it's a **separate analysis**. It is not part of this one, and outputs shouldn't be shaped around it.

---

## 3. What the mentor taught (from the transcript and slide)

**Core principle.** A good strategist finds pain points and angles. A great strategist finds **when** they show up and **why**: the exact moment in the year, week and day the "I have a problem" thought fires. Real-world situations, not marketing situations.

**Example.** A 57-year-old woman and a weight-loss supplement.
- Weak: "She wants to lose weight." Obvious, and every competitor knows it.
- Strong: she's getting dressed for lunch with a friend who just lost a lot of weight, her jeans don't fit, she doesn't know how she'll compare, and she's anxious before stepping out.

**Why hyper-specific.** Meta's Andromeda update is an interest-based algorithm that wants hyper-specific content. A hyper-specific situation gives you something to write toward, somewhere to put the camera, a creator to cast and a story to tell.

**The mentor's slide, "Where to Research Micro Moments":**

| When you need… | Go here | Look for… | Why this matters |
|---|---|---|---|
| Real trigger moments and daily friction | Reddit threads, Facebook Groups, niche forums | Specific situations in first person ("I was at the dentist and…") | First-person stories become ad scripts. The more specific the moment, the more the audience feels seen. |
| Emotional language around the problem | Amazon reviews (1★ and 5★), Trustpilot | Before/after descriptions, what finally made them buy, what they wish they'd known | 5★ shows what to promise. 1★ shows the objections to address up front. |
| Unfiltered customer voice | Qualitative surveys, quiz data, CS tickets | Why they bought NOW, not why they bought in general | "Why now" is the trigger: what tipped them from thinking to buying. That's the hook. |
| Social comparison moments | TikTok/Instagram comments on related content | What people tag friends in, what gets "this is SO me" | Proof that a moment is emotionally strong enough to share. Tagging = creative energy. |

Extra details from the spoken transcript:
- Compare **5★, 3★ and 1★** reviews to find objections. The slide shows only 1★ and 5★; Vojtech ruled the mentor is right either way, so use all three.
- Social comparison is also about how people perceive the whole category (beef snacks, streetwear, dog leashes).
- The mentor uses this for brand audits.

---

## 4. Vojtech's decisions (all locked)

### Structure
- There are **four separate tasks with four separate outputs**, not steps toward one goal. Call them **Task 1–4 (T1–T4)**. They cross-reference each other through IDs.
- **T1 (trigger moments) and T2 (emotional language) are the basics.** They're mandatory, used for about 99% of ads, and must be done extremely well.
- **T3 (why now) and T4 (social comparison) are strategist fuel.** In Vojtech's experience the best ideas had their base in T1/T2, but the difference-maker came from T3. T4 is a variation of T3.
- T3 and T4 **stop at ranked evidence**, with no hooks or ad concepts. Vojtech does the creative work from there.

### The emotional chain (T1)
Finding the moment alone is what mediocre researchers do. Each moment needs:

**what** → **catalyst** (an intermediary, often present but not always) → **why she cares** → **driver** (what's specifically behind the caring)

- The same moment with a different catalyst is a different ad:
  - friend lost weight → "I'll look fat next to her"
  - friend is pretty → "I'll be invisible next to her"
  - friend is rich → "fitness was the one thing I had on her, now we're equal"
  - no catalyst → "my body isn't mine since menopause"
- The persona description usually makes the right chain obvious, so expect **one chain per moment**, and two only if the persona leaves it open.

### The driver layer = whatever is still unclear
1. Check whether "why she cares" already explains the motivator.
   - If it doesn't, answer that first.
   - If it does, ask the next open question: in what specific scenario does it hit, and why does that bother her?
2. List driver hypotheses, both from the data and from reasoning beyond it. For example:
   - others will see the contrast and laugh
   - the friend will judge her
   - photos
   - it shows she's undisciplined, a mark on her name (more common in men)
3. Validate against the data. Two possible outcomes:
   - **A.** The hypotheses are confirmed. One driver may win on both axes, or they split.
   - **B.** New drivers turn up.
4. Rank on **volume** (quantity) and **intensity** (quality), and keep both. E.g. a 35% and a 30% driver reach the most people, while a 10% driver with very high intensity is where quality ads come from.
5. Confidence will usually be vague. That's accepted, but it must be labelled honestly.

### Depth: three whys, then a checkpoint
- Ask "why" **three times** per chain.
- Then show Vojtech a **pop-up (AskUserQuestion)** with the what and the three whys, up to 4 chains per pop-up. Options: **Stop here / Do one more / Do X more** (Vojtech types X under "Other"). Keep going until Vojtech picks "stop here".
- How Vojtech reads the levels, from the jeans example:

| Level | Example | Verdict |
|---|---|---|
| Internal | "She feels insecure" | In her head, hard to show in an ad |
| **Visible** | "She'll look fat next to her friend" | **Headline driver.** Showable, joke-able, can be exaggerated. The main selling point to the client. Deep enough for about 90% of people |
| **Social** | "Others will see the contrast and laugh" | **Supporting layer**, the "final nail in the coffin". Humans are social animals |
| Too deep | "Afraid of losing her place in her social circle" | Awkward and too heavy. Note it, don't lead with it |

### Intensity scoring
- Score **three signals**: language strength, behaviour change (does the moment change what they do?), and engagement.
- **The weights are set for each analysis**, based on the nature of the data (e.g. 60/25/15, 90/10/0, 30/30/40). Record the weights and one line on why. Vojtech confirms them at the end.

### Volumes
- **T1:** scan wide (roughly 15–25 candidates), then **keep 3 moments, expanding to 5** only if the data supports it.
  - Moments supplied with the persona description count toward the 3. If only 1–2 are supplied, still explore for more.
  - Add a one-line "why selected" for each, plus an "also seen" runners-up list.
- **T2:** about 40–60 language cards. **T3:** at least 15 entries. **T4:** about 8–15 cards. Vojtech confirmed these are enough.
- For every task, also stop when new sources only repeat what's already been found.

### Per-task decisions
- **T2:**
  - Scope is the **client's reviews only**. After the whole analysis, **offer** a rerun on client plus competitor reviews.
  - Objections get **no** why-chain. Each just gets a line that addresses it.
  - Quotes are tagged to a T1 chain and layer.
- **T3:**
  - If there's no owned data, **run it anyway** on public timing language ("finally bought it after…") and mark it lower confidence.
  - Keep the last straw and the enabling condition separate.
- **T4:**
  - Search and rank at **category level**, but attach the persona(s) each moment speaks to. These tags are for reference only and don't affect the ranking.
  - Flag high-energy moments that fit no persona.
  - New moments go **back to T1** for the full treatment.

### Process
- Step 0: get inputs (final personas, client and product, review links, any owned data).
- Then do an **access check** of the sources (Reddit, Amazon, Trustpilot, TikTok, Instagram), and say which ones Vojtech needs to supply as exports or screenshots.
- Run **one persona fully through all four tasks first**, then scale to the rest.

### Output format (for each analysis)
- An **MD file** as Claude's working database.
- An **HTML file** for Vojtech, built from `assets/report-template.html`. Vojtech finds MD near impossible to read, so everything they need to see goes in the HTML or a pop-up.
- **IDs:** `[PERSONA]-[TASK]-[NN]`, e.g. `W57-T1-03`. Chains add a letter (`W57-T1-03a`) and drivers add `-D#`. In the HTML, IDs are clickable links.

---

## 5. How to work with Vojtech
- **"AD carry method" / "daughter method":** give Vojtech the basics and leave them free. They'll keep criticising the basics and pushing past them.
  - Vojtech often talks about basics as if they don't matter or "removes the credit" from them. That's their style, not a signal to cut corners. They build the basics themself, so the basics must be done extremely well.
  - This is also saved in Vojtech's Notion Memory as "Working style: the basics vs. the next level".
- Deliver evidence and rankings. Vojtech does the creative jump.
- Use pop-ups with concrete options for decisions.
- Vojtech's terms: "tasks", not "steps", for T1–T4. "Moment", "chain", "driver". "Quality vs. quantity" means intensity vs. volume.
- Vojtech speaks via voice transcription, so expect typos (e.g. "genes" = jeans, "Andromeda" = Meta's ad update).

---

## 6. Next step
Start the first real run. Ask Vojtech for:
1. **One** final persona, with its description (and any moments that come with it).
2. The client and product.
3. The client's Amazon and Trustpilot review links.
4. Any owned data (surveys, quiz data, CS tickets).

Then follow `SKILL.md`: Step 0 (setup and access check), then T1 through T4, then final assembly. Expect to adjust the skill after this first run, for example source access or realistic card counts.
