# Benchmark Collection of LLM-Based Mental Health Dialogue Datasets

This repository provides a **chronologically organized collection of open-source dialogue datasets** in the field of **AI for mental health**.
The datasets span from early counseling generation (PsyQA, 2021) to structured, safe, and long-context benchmarks (MentalChat-16K, 2025).
They serve as the **core benchmarks for evaluating and advancing LLM-based empathy, diagnostic reasoning, and safety**.

Each entry now records two fields that most papers bury in methods text, or omit:

| Field | Values | Meaning |
|:--|:--|:--|
| **Origin** | Real / Hybrid / Synthetic | *Real* = human-written dialogues or public Q&A. *Hybrid* = a real seed (forum post, case report, or transcript) expanded or reconstructed by an LLM. *Synthetic* = fully model-generated, including LLM-to-LLM role-play. |
| **Age / Adolescent** | Yes / No / Unknown / Minority | Whether help-seekers are **adolescents (WHO 10–19)**. *Minority* = a small teen slice exists, but the corpus is not adolescent-primary. *Unknown* = papers do not report age. |

**Coverage note:** among the originally listed corpora, none is adolescent-primary. [DeepWell-Adol](https://aclanthology.org/2025.emnlp-main.646/) is included below as the open dialogue dataset that actually collects from adolescents (Chinese). For **English** corpora that *might* include ages **12–21**, see [English datasets that might include ages 12–21](#english-datasets-that-might-include-ages-1221).

---

## Summary

| Dataset | Year | Language | Origin | Age / Adolescent | Scale |
|:--|:--:|:--:|:--|:--|:--|
| PsyQA | 2021 | Chinese | Real | Unknown | ≈ 22K QA pairs |
| ESConv | 2022 | English | Real | No | 1.3K dialogues |
| SoulChatCorpus | 2023 | Chinese | Hybrid | No | 2.3M multi-turn |
| Amod / CounselChat | 2023 | English | Real | Unknown | ≈ 2K QA pairs |
| AugESC | 2023 | English | Synthetic | No | 65K–130K dialogues |
| SMILE / MeChat | 2024 | Chinese | Hybrid | Unknown | 55K dialogues |
| CPsyCoun | 2024 | Chinese | Hybrid | Unknown | 3.1K + 500 eval |
| CACTUS | 2024 | English | Synthetic | Minority (10–19 = 1.83%) | 31.6K sessions |
| SimPsyDial | 2024 | English | Synthetic | No | 1K–10K simulated sessions |
| PsyDial | 2025 | Chinese | Hybrid | Unknown | 2,382 long dialogues |
| MDD-5k | 2025 | Chinese | Hybrid | Minority (~90% aged 20–40) | 5K conversations |
| MHSD / MedAgent | 2025 | English | Synthetic | No | 2,284 conversations |
| CounseLLMe | 2025 | English / Italian | Synthetic | No | 400 dialogues |
| HamRaz | 2025 | Persian | Hybrid | Unknown | ~3K–4K dialogues |
| MentalChat-16K | 2025 | English | Hybrid | No (caregivers mean age 60.3) | 16K QA pairs |
| Between Help and Harm | 2025 | English | Hybrid | Unknown | 2K crisis scenarios |
| MusPsy | 2025 | English | Hybrid | Unknown | 1.4K clients × ~6 sessions |
| Psy-Insight | 2025 | Chinese + English | Real | Unknown | 10K bilingual dialogues |
| DeepWell-Adol | 2025 | Chinese | Hybrid | **Yes** (Mage = 13.51) | 1,795 dialogues |

---

## Dataset List (Chronological Evolution)

### Foundational Stage (2021–2022)

#### [PsyQA](https://arxiv.org/abs/2106.01702)
- **Task:** Counseling text generation for mental health support
- **Scope:** Single-turn QA with both short and long counseling responses
- **Language:** Chinese
- **Scale:** ≈ 22K question–answer pairs
- **Origin:** Real — crawled from the Q&A column of Yixinli (`xinli001.com/qa`); answers from trained volunteers and professional counselors
- **Age / Adolescent:** Unknown — general public forum; topics include student/child growth, but no age statistics are published
- **Source:** Chinese online mental-health forums with expert curation
- **Evaluation:** BLEU ≈ 14.3, ROUGE-L ≈ 19.0, Human Empathy ≈ 3.8 / 5
- **Impact:** Foundation dataset later extended by SoulChat (2023) and SMILE (2024)

---

### Empathy Expansion Stage (2023)

#### [SoulChatCorpus](https://github.com/scutcyr/SoulChat)
- **Task:** Empathy, listening, and comfort enhancement
- **Scope:** Labeled empathy stages + large-scale emotional diversity
- **Language:** Chinese
- **Scale:** 2.3M multi-turn dialogues
- **Origin:** Hybrid — crowdsourced single-turn long-text QA, then rewritten by ChatGPT (99% GPT-3.5, 1% GPT-4) into multi-turn empathy dialogues
- **Age / Adolescent:** No — age is not reported; the paper notes that adult vs adolescent empathy needs differ, and the corpus is not age-stratified
- **Model:** Fine-tuned GLM-6B for emotional alignment
- **Significance:** First large-scale empathy-tuning corpus for Chinese LLMs

---

### Dialogue Expansion Stage (2024)

#### [SMILE / MeChat](https://huggingface.co/qiuhuachuan/MeChat)
- **Task:** Multi-turn mental-health support via ChatGPT expansion
- **Scope:** Converts single-turn PsyQA into ~10-turn dialogues
- **Language:** Chinese
- **Scale:** 55K dialogues (~10 turns each)
- **Origin:** Hybrid — real PsyQA QA pairs expanded by ChatGPT into multi-turn conversations
- **Age / Adolescent:** Unknown — inherits PsyQA’s unreported help-seeker ages; no age labels added
- **Evaluation:** MeChat BLEU ≈ 0.42, Human Empathy ≈ 4.1 / 5
- **Output:** MeChat chatbot fine-tuned on SmileChat data

---

### Privacy-Preserving Long Dialogue (2025)

#### [PsyDial](https://aclanthology.org/2025.acl-long.1049.pdf)
- **Task:** Long-term mental-health dialogue generation under privacy constraints
- **Scope:** RMRR (Retrieve, Mask, Reconstruct, Refine) reconstruction of real therapy sessions; annotated for empathy and stage progression
- **Language:** Chinese
- **Scale:** 2,382 multi-turn dialogues (avg. 37.8 turns)
- **Origin:** Hybrid — real client–counselor dialogues (Xinling); client utterances masked and reconstructed by GPT-4o; counselor turns reviewed by experts
- **Age / Adolescent:** Unknown — personally identifiable information, including age, is rewritten for privacy; setting is long-term counseling, not youth-specific
- **Evaluation:** BLEU ≈ 18.7, BERTScore ≈ 0.89, Human Empathy ≈ 4.6 / 5
- **Unique Point:** First benchmark balancing realism and confidentiality in long-context counseling

---

### Structured Diagnostic Simulation (2025)

#### [MDD-5k](https://github.com/lemonsis/mdd-5k)
- **Task:** Clinical diagnosis & treatment simulation
- **Scope:** Structured DSM-5-style diagnostic dialogue
- **Language:** Chinese
- **Scale:** 5,000 doctor–patient conversations from ~1,000 de-identified real patient cases
- **Origin:** Hybrid — real anonymized cases from Shanghai Mental Health Center; conversations synthesized by a neuro-symbolic multi-agent LLM framework. Seed cases are not released publicly.
- **Age / Adolescent:** Minority — about 90% of seed patients are aged 20–40; age is rounded to the nearest ten. The inquiry tree includes teenagers (<20), but they are not the majority.
- **Method:** Generated via neuro-symbolic multi-agent simulation, guided by 1000 de-identified real patient cases (used as seed clinical knowledge, not released publicly).

#### [MHSD / MedAgent (Mental Health Sensemaking Dialogue)](https://arxiv.org/abs/2505.20201)
- **Task:** Diagnostic reasoning and human-centric evaluation
- **Scope:** MultiSenseEval framework — empathy, coherence, personalization, risk awareness
- **Language:** English
- **Scale:** 2,284 patient–assistant conversations
- **Origin:** Synthetic — MedAgent LLM-to-LLM generation (GPT-4o as patient; DeepSeek-R1 / OpenAI o1 as sensemaker)
- **Age / Adolescent:** No — synthetic adult patient personas for diagnostic/sensemaking evaluation
- **Insight:** Measures long-context degradation and alignment with patient values
- **Availability:** *Dataset not yet publicly released (authors announced future open-sourcing). Code/data link pending publication.*

---

### Cross-Cultural Therapy Benchmarks (2024–2025)

#### [CounseLLMe](https://osf.io/2ay8d/)
- **Task:** Simulated therapy comparing LLM vs. human dialogues
- **Scope:** Trust, conflict, and emotional structures (English / Italian)
- **Scale:** 400 dialogues × 20 turns
- **Origin:** Synthetic — LLM-to-LLM dialogues (GPT-3.5 and Claude-3 Haiku for English; Claude-3 Haiku and LLaMAntino for Italian), with therapist-designed prompts
- **Age / Adolescent:** No — simulated adult patient–therapist conversations on depression
- **Method:** GPT-3.5 + Claude Haiku with therapist-designed prompts

#### [HamRaz](https://arxiv.org/abs/2502.05982)
- **Task:** Person-Centered Therapy (PCT) in Persian
- **Scope:** Culturally adapted empathy evaluation (HamRazEval)
- **Language:** Persian
- **Scale:** ~3K dialogues (seeded from ~4K crawled forum questions)
- **Origin:** Hybrid — real user questions from Iranian psychology forums; PCT sessions generated by LLM agents (script + role-play)
- **Age / Adolescent:** Unknown — age is extracted as a per-post contextual factor, with no aggregate stats. Topic list includes “behavioral issues in youth,” but the corpus is not youth-only.
- **Focus:** Cross-cultural authenticity and therapeutic realism

---

### Unified Integration & Safety Evaluation (2025)

#### [MentalChat-16K](https://arxiv.org/abs/2503.13509v1)
- **Task:** Long-context mental-health counseling
- **Scope:** Empathy + reasoning + safety (symptom, risk, intervention tags)
- **Language:** English
- **Scale:** 16K dialogues (6,338 paraphrased interviews + 9,775 GPT-3.5 conversations)
- **Origin:** Hybrid — real PISCES hospice-caregiver interview transcripts (paraphrased locally with Mistral) plus GPT-3.5 Turbo synthetic counseling
- **Age / Adolescent:** No — real subset is family caregivers of palliative/hospice patients; mean age 60.3 (range 19–100; inclusion criterion 18+)
- **Source:** Real caregiver transcripts + GPT-generated augmentations
- **Evaluation:** GPT-4 & Gemini automatic + expert review

#### [Between Help and Harm](https://arxiv.org/html/2509.24857v1)
- **Task:** Mental-health crisis handling & safety evaluation
- **Scope:** Six crisis categories (suicidal, self-harm, violence, etc.)
- **Language:** English
- **Scale:** ~2K crisis scenarios (2,252 curated examples)
- **Origin:** Hybrid — merged from 12 public Hugging Face datasets (forums, transcripts, synthetic, mixed human–AI)
- **Age / Adolescent:** Unknown — crisis taxonomy, not an age-stratified youth crisis set
- **Goal:** Benchmarking LLMs’ adequacy under high-risk contexts

---

### Adolescent-Primary Corpus (2025)

#### [DeepWell-Adol](https://aclanthology.org/2025.emnlp-main.646/) ([GitHub](https://github.com/DeepWell-Adol/DeepWell-Adolescent))
EMNLP 2025, Tsinghua Shenzhen International Graduate School. This is currently the **only adolescent-primary corpus** in this collection.

**What it is.** A Chinese multi-turn coaching corpus for *positive* adolescent mental health (positive psychology + coaching), not CBT diagnosis or crisis counseling. Existing datasets (PsyQA, SoulChat, SMILE, CPsyCoun) mostly cover general-population counseling, empathy, or symptom management. DeepWell targets developmental issues — academics, peers, identity — with prevention and growth rather than clinical treatment.

**Who the adolescents are.** Age is reported. A paper survey collected 125 responses from 87 students (Mage = 13.51, SD = 2.59; Grades 2–12). The main range is 10–19; eight ages 7–9 were kept. Experts selected 87 complete scenarios and wrote dialogues from them. **Age comes from real adolescent questionnaires; the dialogues themselves are not transcribed therapy sessions.**

**How it was built (Hybrid).** 1,795 multi-turn dialogues in two parts:

| Split | Size | Construction |
|:--|:--|:--|
| Expert-written | 925 (from 1,139 drafted) | 51 adolescent-MH experts; mean 8.69 years of experience; ~43% are primary/secondary school counseling teachers |
| LLM-expanded | 870 | DeepSynergy: GLM-4-Plus writes an intervention plan, then the dialogue |

Expert dialogues average 6.88 turns; generated dialogues 13.18 turns. Screening requires roughly ages 8–18, 5–10 rounds, **no crisis intervention, and no suicidal/self-harm content**. This is wellbeing coaching, not a clinical or crisis corpus.

**Themes** (expert split): emotion regulation 147; academic & career 251; social & interpersonal 363; lifestyle & environment 89; personal growth & identity 75. Dialogues follow a six-stage coaching script: build rapport → clarify the issue → find strengths/resources → imagine a preferred future → set goals → summarize and transfer.

**Results, in brief.** On standard counseling/empathy metrics it matches or slightly beats SMILECHAT and CPsyCounD; it leads more clearly on positive-psychology outcomes (positive processes, character strengths, healthy behaviors). LoRA fine-tuning Qwen2.5-7B / ChatGLM3-6B / Baichuan2-7B works best when expert-written and generated data are combined. Ethics approval: Life Ethics Committee, Tsinghua SIGS (F151, 2024).

**Boundary for use.** Treat it as *real adolescent scenarios + expert/LLM-written coaching dialogues*, not real adolescent counseling transcripts. Suitable for youth wellbeing-support models. Not suitable as training data for crisis intervention, clinical diagnosis, or authentic adolescent speech. Chinese only; the authors note limited cultural and developmental coverage.
- **Task:** Positive mental health and wellbeing coaching for adolescents
- **Scope:** Emotion regulation, academic/career development, social relationships, lifestyle adaptation, personal growth
- **Language:** Chinese
- **Scale:** 1,795 multi-turn dialogues (925 expert-written + 870 GLM-4 expanded)
- **Origin:** Hybrid — real adolescent survey scenarios (n = 87) plus expert-written seed dialogues, then two-stage LLM augmentation
- **Age / Adolescent:** **Yes** — primarily ages 10–19 (Mage = 13.51, SD = 2.59, Grades 2–12; a few ages 7–9 retained)
- **Why it matters:** This is the open dialogue corpus that actually collects from adolescents, which the rest of this list does not.

---

## Supplementary Benchmarks (Cross-Year Additions)

To complement the chronological collection, the following open-source datasets further broaden the landscape of **LLM-based mental-health dialogues** across emotional support, cognitive-behavioural therapy, bilingual reasoning, and long-term counselling simulation.

| Dataset | Year | Language | Origin | Age / Adolescent | Task / Focus | Scale | Notable Features | Source |
|:--|:--:|:--:|:--|:--|:--|:--|:--|:--|
| **ESConv** | 2022 | English | Real | No — crowdworkers typically 18+; some topics (academic pressure, school bullying) are adolescent-relevant | Emotional support conversation | 1.3K dialogues (~29.5 turns avg.) | 8 support strategies × 3 problem types; empathy-oriented counselling | [GitHub](https://github.com/thu-coai/Emotional-Support-Conversation) |
| **AugESC** | 2023 | English | Synthetic | No | Augmented emotional support | 65K–130K dialogues (GPT-J generated) | ~45–100× larger than ESConv; improved strategy diversity | [arXiv:2202.13047](https://arxiv.org/abs/2202.13047) |
| **MusPsy-Dataset** | 2025 | English | Hybrid | Unknown — age is a static profile field; no published distribution | Multi-session psychological counselling | 1.4K clients × ~6 sessions | Real published case reports as profiles; LLM-generated longitudinal sessions | [arXiv:2501.09473](https://arxiv.org/abs/2501.09473) / [arXiv:2506.06626](https://arxiv.org/abs/2506.06626) |
| **CACTUS** | 2024 | English | Synthetic | Minority — synthetic personas; 10–19 years = 1.83%; mostly 20–39 | Cognitive-Behavioural Therapy (CBT) corpus | 31.6K sessions | Columns: *thought*, *patterns*, *cbt_technique*, *plan*, *dialogue* | [HuggingFace](https://huggingface.co/datasets/LangAGI-Lab/cactus) |
| **CPsyCoun** | 2024 | Chinese | Hybrid | Unknown — has an Education topic; client age in source reports is not published | Counselling dialogues + evaluation | 3.1K (CPsyCounD) + 500 eval (CPsyCounE) | Real public counseling reports reconstructed via Memo2Demo (GLM-4) | [GitHub](https://github.com/X-D-Lab/CPsyCoun) |
| **Amod Mental-Health Conversations** | 2023 | English | Real | Unknown | FAQ-style Q/A chatbot data | ~2K pairs | Real anonymized CounselChat.com therapy Q&A | [HuggingFace](https://huggingface.co/datasets/Amod/mental_health_counseling_conversations) |
| **Psy-Insight** | 2025 | Chinese + English | Real | Unknown | Explainable bilingual counselling | 10K bilingual dialogues (6,208 EN / 4,310 ZH rounds) | Face-to-face counseling from blogs and books; annotated for reasoning, emotion, treatment strategy | [GitHub](https://github.com/NJUPsyAI/Psy-Insight) |
| **SimPsyDial** | 2024 | English | Synthetic | No | Simulated LLM-to-LLM psychological counselling | 1K–10K simulated sessions | Multi-agent role-play with controllable empathy levels | [arXiv:2408.15787](https://arxiv.org/abs/2408.15787) |

> These supplementary datasets extend the benchmark scope beyond the core timeline, adding realism, cross-lingual reasoning, and explainability dimensions for future evaluation.

---

## English datasets that might include ages 12–21

César asked for English-language corpora that **might** contain people aged **12–21**. Below is a briefing in the same spirit as the CACTUS / DeepWell notes. Important framing:

- **No English dataset in this list is adolescent-primary** the way DeepWell-Adol is (Chinese; Mage = 13.51).
- Ages **12–21** mix mid-adolescence and early adulthood. A hit on “student,” “school,” or “academic pressure” is **not** proof of age 12–21.
- Prefer corpora with an **explicit, filterable age field**. Topic-only evidence is weak.

### Quick ranking for a 12–21 English option

| Priority | Dataset | Why | 12–21 status |
|:--:|:--|:--|:--|
| 1 | **CACTUS** | Only large English set with parseable age in each row | Filterable synthetic personas; paper: 10–19 = 1.83% (~580 of 31.6K). Ages 20–21 sit inside the large 20–29 band (22.18%) |
| 2 | **MusPsy** | Age is a static profile trait from real case reports | Filterable **if** released profiles expose age; no published 12–21 %. Examples include high-school clients |
| 3 | **ESConv** (+ **AugESC**) | Youth-relevant *topics* only | No age field. Academic pressure 156; school bullying 2 of ~1.3K. Crowdworkers typically 18+ |
| 4 | **Amod / CounselChat** | Real English therapy Q&A | No age field; may *mention* teens in free text |
| 5 | **MentalChat-16K** | Strong English hybrid benchmark | Real half: caregivers, mean 60.3, inclusion **18+**, range 19–100 → only a thin 19–21 tip possible. Synthetic half: no age labels |
| — | SimPsyDial, MHSD, CounseLLMe, Between Help and Harm, Psy-Insight (EN) | English (or bilingual) but not age-usable for 12–21 | No usable age stratification; adult / unknown |

### Detail cards (English only)

#### [CACTUS](https://huggingface.co/datasets/LangAGI-Lab/cactus) — best English *filterable* option
- **Who / where:** Yonsei University (LangAGI-Lab). EMNLP 2024 Findings. Authors: Suyeon Lee, Sunghwan Kim, Minju Kim (equal); corresponding: Jinyoung Yeo. Code: https://github.com/coding-groot/cactus
- **What:** Fully **synthetic** English CBT multi-turn counseling. 31,577 dialogues (~16.6 turns). GPT-4o script-mode generation; CTRS filter (mean ≥ 5). Downstream model: **CAMEL**
- **Fields:** `thought`, `patterns`, `intake_form` (contains `Age:`), `cbt_technique`, `cbt_plan`, `attitude`, `dialogue`
- **12–21:** Parse `Age` from `intake_form`. Paper Table 9: **10–19 = 1.83%**; **20–29 = 22.18%**. So a strict teen band is small (~580); extending to 21 adds whatever share of 20–21 exists inside 20–29 (not published year-by-year)
- **Caveat:** Age is an LLM-assigned persona, not a real client. Persona text can be incoherent (e.g. Age = 12 with college/career failure). Any 12–21 subset needs manual QC. Adult CBT framing, not adolescent developmental design

#### [MusPsy](https://arxiv.org/abs/2506.06626) — age in profiles, distribution unknown
- **What:** Hybrid multi-session CBT. ~1,400 clients × ~6 sessions. Profiles from published case reports; dialogues LLM-generated
- **12–21:** Static traits include **age**, gender, occupation. Paper examples include high-school (e.g. Grade 2) clients. **No aggregate age table** is published, so 12–21 count is unknown until profiles are audited
- **Caveat:** Dialogues are synthetic expansions of case-report seeds, not session transcripts

#### [ESConv](https://github.com/thu-coai/Emotional-Support-Conversation) — topic proxy only
- **What:** Real crowdsourced emotional-support dialogues (~1.3K). Help-seeker / supporter role-play
- **12–21:** **No age field.** Youth-adjacent problem tags: academic pressure (156), school bullying (2), issues with parent (18), appearance anxiety (12). Crowd platforms typically require adults (18+)
- **Caveat:** Topic ≠ speaker age. Do not treat academic-pressure chats as a teen corpus

#### [AugESC](https://arxiv.org/abs/2202.13047) — synthetic expansion of ESConv
- **What:** GPT-J–augmented ESC (~65K–130K). Same domain as ESConv
- **12–21:** Same limitation: no age labels; only topic continuity with ESConv

#### [Amod / CounselChat](https://huggingface.co/datasets/Amod/mental_health_counseling_conversations) — real Q&A, no age
- **What:** ~2K real English counseling Q&A from CounselChat.com (licensed therapists)
- **12–21:** No demographic table. Free-text questions may discuss teens/parents/school, but askers’ ages are unpublished
- **Caveat:** Cannot filter to 12–21 without unsupervised text heuristics (noisy)

#### [MentalChat-16K](https://arxiv.org/abs/2503.13509) — adult caregivers + unaged synthetic
- **What:** Hybrid English. 6,338 paraphrased PISCES hospice-caregiver interviews + 9,775 GPT-3.5 counseling QA (33 topics)
- **12–21:** Real half inclusion **18+**, mean age **60.3**, reported range **19–100** → at most a thin early-adult tip (19–21), not adolescents. Synthetic half has **no age field**
- **Caveat:** Excellent general English MH resource; poor fit as a youth corpus

#### [Between Help and Harm](https://arxiv.org/html/2509.24857v1) — crisis inputs, no age
- **What:** ~2,252 English crisis-user inputs curated from 12 HF sources for safety evaluation
- **12–21:** No age metadata. Crisis *language* may include youth contexts; speakers are not age-labeled

#### [SimPsyDial](https://arxiv.org/abs/2408.15787) / [MHSD](https://arxiv.org/abs/2505.20201) / [CounseLLMe](https://osf.io/2ay8d/) — synthetic adults
- **SimPsyDial:** LLM–LLM counseling; no age stratification published
- **MHSD / MedAgent:** 2,284 synthetic diagnostic dialogues; adult patient personas; dataset release pending
- **CounseLLMe:** 400 EN/IT simulated depression dialogues; adult patient–therapist framing
- **12–21:** Not usable as youth-labeled English data without new annotation

#### [Psy-Insight](https://github.com/NJUPsyAI/Psy-Insight) (English half) — real counseling style, age unpublished
- **What:** Bilingual explainable counseling; English portion ~6,208 turns / 520 sessions from blogs and books
- **12–21:** No published age distribution for clients

### Practical recommendation for ages 12–21 (English)

1. **Keep CACTUS as the primary English option** and build a QC’d `Age ∈ [12, 21]` subset from `intake_form`.
2. **Audit MusPsy profiles** next, if the release exposes age — real case-report ages are more trustworthy than CACTUS personas, but dialogues remain generated.
3. Use **ESConv / AugESC / CounselChat** only as weak topic-side evidence, not as age-verified youth data.
4. For **true adolescent collection** (survey-grounded ages), the list still points to **DeepWell-Adol** — Chinese only.

---

## How to read Origin and Age

1. **Origin = Hybrid is the majority pattern.** Most large counseling corpora start from a real seed and then use an LLM to expand, reconstruct, or role-play. Treat them as neither fully clinical nor fully synthetic.
2. **Age is usually unpublished.** Forum crawls (PsyQA, HamRaz, Amod) and reconstructed reports (CPsyCoun, PsyDial, MusPsy) almost never release help-seeker age.
3. **Adolescent ≠ adolescent-relevant topics.** Academic pressure, school bullying, or “youth behavior” tags do not mean the speakers were adolescents. ESConv, PsyQA, and HamRaz may *talk about* youth issues while being collected from general/adult users.
4. **Known adult-skewed corpora:** MentalChat-16K real subset (hospice caregivers, mean age 60.3); MDD-5k (~90% aged 20–40); CACTUS (paper: teen personas 10–19 = 1.83%).
5. **Ages 12–21 (English):** see the dedicated section above. Filterable age ≈ CACTUS (+ possibly MusPsy). Everything else is topic-only or unknown.

---

## Labeling convention for future entries

When adding a dataset, fill both fields even if the paper is silent:

```text
- **Origin:** Real | Hybrid | Synthetic — <one-line construction method>
- **Age / Adolescent:** Yes | No | Unknown | Minority — <age stats or “not reported”>
```

If age is not in the paper, write **Unknown**, not an inferred demographic.
