
# 🧠 Benchmark Collection of LLM-Based Mental Health Dialogue Datasets

This repository provides a **chronologically organized collection of open-source dialogue datasets** in the field of **AI for mental health**.  
The datasets span from early counseling generation (PsyQA, 2021) to structured, safe, and long-context benchmarks (MentalChat-16K, 2025).  
They serve as the **core benchmarks for evaluating and advancing LLM-based empathy, diagnostic reasoning, and safety**.

---

## 📂 Dataset List (Chronological Evolution)

### 🩺 Foundational Stage (2021–2022)

#### [PsyQA](https://arxiv.org/abs/2106.01702)
- **Task:** Counseling text generation for mental health support  
- **Scope:** Single-turn QA with both short and long counseling responses  
- **Language:** Chinese  
- **Scale:** ≈ 22 K question–answer pairs  
- **Source:** Chinese online mental-health forums with expert curation  
- **Evaluation:** BLEU ≈ 14.3, ROUGE-L ≈ 19.0, Human Empathy ≈ 3.8 / 5  
- **Impact:** Foundation dataset later extended by SoulChat (2023) and SMILE (2024)

---

### 💬 Empathy Expansion Stage (2023)

#### [SoulChatCorpus](https://github.com/scutcyr/SoulChat)
- **Task:** Empathy, listening, and comfort enhancement  
- **Scope:** Labeled empathy stages + large-scale emotional diversity  
- **Language:** Chinese  
- **Scale:** 2.3 M multi-turn dialogues  
- **Model:** Fine-tuned GLM-6B for emotional alignment  
- **Significance:** First large-scale empathy-tuning corpus for Chinese LLMs

---

### 🔄 Dialogue Expansion Stage (2024)

#### [SMILE / MeChat](https://huggingface.co/qiuhuachuan/MeChat)
- **Task:** Multi-turn mental-health support via ChatGPT expansion  
- **Scope:** Converts single-turn PsyQA into 10-turn dialogues  
- **Language:** Chinese  
- **Scale:** 55 K dialogues (~10 turns each)  
- **Evaluation:** MeChat BLEU ≈ 0.42, Human Empathy ≈ 4.1 / 5  
- **Output:** MeChat chatbot fine-tuned on SmileChat data  

---

### 🔒 Privacy-Preserving Long Dialogue (2025)

#### [PsyDial](https://aclanthology.org/2025.acl-long.1049.pdf)
- **Task:** Long-term mental-health dialogue generation under privacy constraints  
- **Scope:** RMRR privacy-preserving reconstruction of real therapy sessions; annotated for empathy and stage progression  
- **Language:** English  
- **Scale:** ~10 K multi-turn dialogues (12–15 turns avg.)  
- **Evaluation:** BLEU ≈ 18.7, BERTScore ≈ 0.89, Human Empathy ≈ 4.6 / 5  
- **Unique Point:** First benchmark balancing realism and confidentiality in long-context counseling  

---

### 🧠 Structured Diagnostic Simulation (2025)

#### [MDD-5k](https://github.com/lemonsis/mdd-5k)
- **Task:** Clinical diagnosis & treatment simulation  
- **Scope:** Structured DSM-5-style diagnostic dialogue  
- **Language:** Chinese  
- **Scale:** 5 000 doctor–patient conversations  
- **Method:** Generated via neuro-symbolic multi-agent simulation, guided by 1000 de-identified real patient cases (used as seed clinical knowledge, not released publicly).  

#### [MHSD / MedAgent (Mental Health Sensemaking Dialogue)](https://arxiv.org/abs/2505.20201)
- **Task:** Diagnostic reasoning and human-centric evaluation  
- **Scope:** MultiSenseEval framework—empathy, coherence, personalization, risk awareness  
- **Language:** English  
- **Scale:** 2 284 patient–assistant conversations  
- **Insight:** Measures long-context degradation and alignment with patient values  
- **Availability:** *Dataset not yet publicly released (authors announced future open-sourcing). Code/data link pending publication.*  

---

### 🌍 Cross-Cultural Therapy Benchmarks (2024–2025)

#### [CounseLLMe](https://osf.io/2ay8d/)
- **Task:** Simulated therapy comparing LLM vs. human dialogues  
- **Scope:** Trust, conflict, and emotional structures (English / Italian)  
- **Scale:** 400 dialogues × 20 turns  
- **Method:** GPT-3.5 + Claude Haiku with therapist-designed prompts  

#### [HamRaz](https://arxiv.org/abs/2502.05982)
- **Task:** Person-Centered Therapy (PCT) in Persian  
- **Scope:** Culturally adapted empathy evaluation (HamRazEval)  
- **Language:** Persian  
- **Scale:** ~3 K dialogues  
- **Focus:** Cross-cultural authenticity and therapeutic realism  

---

### ⚙️ Unified Integration & Safety Evaluation (2025)

#### [MentalChat-16K](https://arxiv.org/abs/2503.13509v1)
- **Task:** Long-context mental-health counseling  
- **Scope:** Empathy + reasoning + safety (symptom, risk, intervention tags)  
- **Language:** English  
- **Scale:** 16 K dialogues  
- **Source:** Real caregiver transcripts + GPT-generated augmentations  
- **Evaluation:** GPT-4 & Gemini automatic + expert review  

#### [Between Help and Harm](https://arxiv.org/html/2509.24857v1)
- **Task:** Mental-health crisis handling & safety evaluation  
- **Scope:** Six crisis categories (suicidal, self-harm, violence, etc.)  
- **Language:** English  
- **Scale:** 2 K crisis scenarios  
- **Goal:** Benchmarking LLMs’ adequacy under high-risk contexts  

---

## 🧩 Supplementary Benchmarks (Cross-Year Additions)

To complement the chronological collection, the following open-source datasets further broaden the landscape of **LLM-based mental-health dialogues** across emotional support, cognitive-behavioural therapy, bilingual reasoning, and long-term counselling simulation.

| Dataset | Year | Language | Task / Focus | Scale | Notable Features | Source |
|:--|:--:|:--:|:--|:--|:--|:--|
| **ESConv** | 2022 | English | Emotional support conversation | 1.3 K dialogues (~29.5 turns avg.) | 8 support strategies × 3 problem types; empathy-oriented counselling | [GitHub](https://github.com/thu-coai/Emotional-Support-Conversation) |
| **AugESC** | 2023 | English | Augmented emotional support | 130 K dialogues (GPT-J generated) | 100× larger than ESConv; improved strategy diversity | [arXiv:2202.13047](https://arxiv.org/abs/2202.13047) |
| **MusPsy-Dataset** | 2025 | English | Multi-session psychological counselling | 1.4 K clients × ~6 sessions | Tracks longitudinal improvement and emotion trajectory | [arXiv:2501.09473](https://arxiv.org/abs/2501.09473) |
| **CACTUS** | 2024 | English | Cognitive-Behavioural Therapy (CBT) corpus | 31.6 K sessions | Columns: *thought*, *patterns*, *cbt_technique*, *plan*, *dialogue* | [HuggingFace](https://huggingface.co/datasets/LangAGI-Lab/cactus) |
| **CPsyCoun** | 2024 | Chinese | Counselling dialogues + evaluation | 3.1 K (CPsyCounD) + 500 eval (CPsyCounE) | Expert-curated with 5 counselling intents and 9 emotion labels | [GitHub](https://github.com/X-D-Lab/CPsyCoun) |
| **Amod Mental-Health Conversations** | 2023 | English | FAQ-style Q/A chatbot data | ~2 K pairs | Real anonymized therapy and support queries | [HuggingFace](https://huggingface.co/datasets/Amod/mental_health_counseling_conversations) |
| **Psy-Insight** | 2025 | Chinese + English | Explainable bilingual counselling | 10 K bilingual dialogues (6,208 EN / 4,310 ZH rounds) | Annotated for reasoning, emotion, treatment strategy | [GitHub](https://github.com/NJUPsyAI/Psy-Insight) |
| **SimPsyDial** | 2024 | English | Simulated LLM-to-LLM psychological counselling | 2 × 10 K simulated sessions | Multi-agent role-play with controllable empathy levels | [arXiv:2408.15787](https://arxiv.org/abs/2408.15787) |

---

> 💡 *These supplementary datasets extend the benchmark scope beyond the core timeline, adding realism, cross-lingual reasoning, and explainability dimensions for future evaluation.*

---
