# 🧠 Benchmark Collection of LLM-Based Mental Health Dialogue Datasets

This repository provides a **curated list of publicly available multi-turn dialogue datasets** in the field of **AI for mental health**.  
All datasets are open-source and designed to support **LLM research** focused on *empathy*, *diagnosis*, *risk assessment*, and *safety evaluation*.

These benchmarks represent today’s leading testbeds—ideal references for future experiments, fine-tuning, or model comparison.

---

## 📂 Dataset List

### 1. [MentalChat-16K](https://github.com/ChiaPatricia/MentalChat16K)
- **Task:** Long-context mental-health counseling  
- **Scope:** Empathy + reasoning + safety (symptom, risk, intervention tags)  
- **Language:** English  
- **Scale:** 16 K dialogues  
- **Source:** Real caregiver transcripts + GPT-generated augmentations  
- **Evaluation:** GPT-4 & Gemini automatic + expert review  

---

### 2. [MedAgent / MHSD (Mental Health Sensemaking Dialogue)](https://arxiv.org/abs/2505.20201)
- **Task:** Diagnostic reasoning and human-centric evaluation  
- **Scope:** MultiSenseEval framework—empathy, coherence, personalization, risk awareness  
- **Language:** English  
- **Scale:** 2 284 patient–assistant conversations  
- **Insight:** Measures long-context degradation and alignment with patient values  
- **Availability:** *Dataset not yet publicly released (authors announced future open-sourcing). Code/data link pending publication.*  


### 3. [MDD-5k](https://github.com/lemonsis/mdd-5k)
- **Task:** Clinical diagnosis & treatment simulation  
- **Scope:** Structured DSM-5-style diagnostic dialogue  
- **Language:** Chinese  
- **Scale:** 5 000 doctor–patient conversations  
- **Method:** Generated through a neuro-symbolic multi-agent simulation framework,
  guided by 1000 de-identified real patient cases (used as seed clinical knowledge, not released publicly).


---

### 4. [PsyDial](https://aclanthology.org/2025.acl-long.1049/)
- **Task:** Long-term psychological support  
- **Scope:** Privacy-preserving (RMRR) reconstruction of real therapy dialogues  
- **Language:** English  
- **Scale:** ~10 K long conversations  
- **Unique Point:** First large-scale dataset balancing realism and confidentiality  

---

### 5. [SMILE / SmileChat](https://huggingface.co/qiuhuachuan/MeChat)
- **Task:** Multi-turn mental-health support via ChatGPT expansion  
- **Scope:** Empathy, suggestion, and emotional progression  
- **Language:** Chinese  
- **Scale:** 55 K dialogues (~10 turns each)  
- **Output:** MeChat chatbot fine-tuned on SmileChat data  

---

### 6. [SoulChatCorpus](https://github.com/scutcyr/SoulChat)
- **Task:** Empathy, listening, and comfort enhancement  
- **Scope:** Labeled empathy stages + large-scale emotional diversity  
- **Language:** Chinese  
- **Scale:** 2.3 M multi-turn dialogues  
- **Model:** Fine-tuned GLM-6B for emotional alignment  

---

### 7. [CounseLLMe](https://osf.io/2ay8d/)
- **Task:** Simulated therapy comparing LLM vs. human dialogues  
- **Scope:** Trust, conflict, and emotional structures (English / Italian)  
- **Scale:** 400 dialogues × 20 turns  
- **Method:** GPT-3.5 + Claude Haiku with prompts crafted by therapists  

---

### 8. [HamRaz](https://arxiv.org/abs/2502.05982)
- **Task:** Person-Centered Therapy (PCT) in Persian  
- **Scope:** Culturally adapted empathy evaluation (HamRazEval)  
- **Language:** Persian  
- **Scale:** ~3 K dialogues  
- **Focus:** Cross-cultural authenticity and therapeutic realism  

---

### 9. [Between Help and Harm](https://arxiv.org/html/2509.24857v1)
- **Task:** Mental-health crisis handling & safety evaluation  
- **Scope:** Six crisis categories (suicidal, self-harm, violence, etc.)  
- **Language:** English  
- **Scale:** 2 K crisis scenarios  
- **Goal:** Benchmarking LLMs’ adequacy under high-risk contexts  

---

## 🧩 Dataset Scope Summary

| Category | Representative Datasets | Core Objective | Key Trend |
|:--|:--|:--|:--|
| **Diagnostic-oriented** | MDD-5k, MHSD, PsyDial | Clinical reasoning, structured diagnosis | Rise of neuro-symbolic & privacy-safe synthetic dialogues |
| **Empathy-focused** | SoulChat, SMILE, MentalChat-16K | Emotional support, comfort, active listening | From surface empathy → structured therapeutic process |
| **Crisis / Safety** | Between Help and Harm | High-risk safety & appropriateness | Shift from harmlessness → helpfulness under risk |
| **Cross-cultural** | HamRaz, CounseLLMe | Cultural / linguistic realism | Expanding beyond English-centric datasets |
| **Benchmark frameworks** | MultiSenseEval, MentalBench | Unified evaluation protocols | Toward standardized, reproducible scoring systems |

---

## 📈 Research Evolution (2023 → 2025)

| Period | Focus | Example Datasets |
|:--|:--|:--|
| **Pre-2023** | Single-turn social-media text (classification) | Reddit, SMHD, Dreaddit |
| **2023–2024** | Empathy-tuned dialogue generation | SoulChat, SMILE |
| **2024–2025** | Structured reasoning + safety evaluation | MDD-5k, MHSD, Between Help and Harm |
| **2025 + Frontier** | Integrated counseling + diagnosis + safety | MentalChat-16K |

---

---

## 📊 Benchmark Evaluation Summary

| Dataset | Evaluation Setting | Reported Metrics / Baselines | Notes |
|:--|:--|:--|:--|
| **MentalChat-16K** | Long-context dialogue generation; human + LLM eval | GPT-4 ≈ 4.5/5 empathy, 0.92 coherence; Gemini slightly lower | Human judges rated empathy & safety alignment |
| **MHSD / MedAgent** | MultiSenseEval (6-dimension human evaluation) | GPT-4-Turbo F1 ≈ 0.86 (diagnosis consistency), 0.81 empathy | Dataset not yet released; results reported in paper only |
| **MDD-5k** | Multi-agent diagnostic reasoning | LLM baseline accuracy ≈ 0.88 DSM-5 compliance | Evaluated on structured diagnosis prediction |
| **PsyDial** | Counseling generation; human coherence test | No numeric metric (qualitative only) | Focus on privacy & continuity, not leaderboard |
| **SMILE / SmileChat** | Emotional support generation | MeChat model BLEU ≈ 0.42, human empathy ≈ 4.1/5 | Trained from GPT-3.5 expanded dialogues |
| **SoulChatCorpus** | Empathy classification + generation | GLM-6B empathy acc ≈ 0.92 | Large-scale pretraining corpus (2.3M dialogues) |
| **HamRaz** | Person-Centered Therapy evaluation | HamRazEval empathy F1 ≈ 0.78 | Cross-cultural benchmark in Persian |
| **CounseLLMe** | Human vs LLM comparison study | No numeric scores (qualitative human study) | Trust/conflict/emotion coded manually |
| **Between Help and Harm** | Safety response adequacy | GPT-4 helpfulness ≈ 0.71 F1; Claude ≈ 0.67 | Evaluated across 6 crisis types |

---

> ⚠️ **Note:** Many benchmarks in this domain rely on *human evaluation or LLM-based scoring* rather than automatic metrics.  
> Numerical results may vary depending on the evaluation rubric and prompt design.

---

## 💡 Future Plan
We plan to expand this section into a **living leaderboard**,  
where future models can be compared across empathy, diagnosis, and safety metrics on these benchmarks.


## 🎯 Research Implication

These datasets together form the **benchmark collection** for LLM-based mental-health dialogue research.  
They define the current **state-of-the-art battlefield**—the standards that upcoming models must **match, evaluate against, and surpass**  
in empathy, diagnostic accuracy, and risk-aware reasoning.

---

## 🤝 Contributing

Contributions are welcome!  
Add new open-source datasets, benchmarks, or evaluation scripts through Pull Requests.

---

## 🧠 Acknowledgement
All credit to the original dataset creators and research teams at  
University of Pennsylvania, UIUC, Zhejiang University, Tsinghua University, ETH Zürich, and others advancing **AI for Mental Health**.

---
