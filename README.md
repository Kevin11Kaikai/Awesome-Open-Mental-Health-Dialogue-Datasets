# 🧠 Benchmark Collection of LLM-Based Mental Health Dialogue Datasets

This repository provides a **chronologically organized collection of open-source multi-turn dialogue datasets** in the field of **AI for mental health**.  
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
- **Scale:** 5，000 doctor–patient conversations  
- **Method:** Generated via neuro-symbolic multi-agent simulation, guided by 1000 de-identified real patient cases (used as seed clinical knowledge, not released publicly).
- **Availability:** *Dataset not yet publicly released (authors announced future open-sourcing). Code/data link pending publication.* 

#### [MHSD / MedAgent (Mental Health Sensemaking Dialogue)](https://arxiv.org/abs/2505.20201)
- **Task:** Diagnostic reasoning and human-centric evaluation  
- **Scope:** MultiSenseEval framework—empathy, coherence, personalization, risk awareness  
- **Language:** English  
- **Scale:** 2，284 patient–assistant conversations  
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

## 📊 Benchmark Evaluation Summary

| Dataset | Evaluation Setting | Reported Metrics / Baselines | Notes |
|:--|:--|:--|:--|
| **PsyQA** | Counseling text generation | BLEU ≈ 14.3, ROUGE-L ≈ 19.0, Human Empathy ≈ 3.8 | Foundation for later corpora |
| **SoulChatCorpus** | Empathy classification + generation | Empathy Accuracy ≈ 0.92 | GLM-6B fine-tuning corpus |
| **SMILE / MeChat** | Emotional support generation | BLEU ≈ 0.42, Human Empathy ≈ 4.1 / 5 | Multi-turn Chinese dialogues |
| **PsyDial** | Long-context privacy-preserving generation | BLEU ≈ 18.7, BERTScore ≈ 0.89, Empathy ≈ 4.6 | ACL 2025 long paper |
| **MDD-5k** | Multi-agent diagnostic reasoning | DSM-5 compliance ≈ 0.88 | Synthetic dataset guided by 1000 real cases |
| **MHSD / MedAgent** | MultiSenseEval (human evaluation) | Diagnosis F1 ≈ 0.86, Empathy ≈ 0.81 | Dataset pending release |
| **CounseLLMe** | Human vs LLM therapy simulation | Qualitative only | Cross-lingual trust/emotion analysis |
| **HamRaz** | Person-Centered Therapy evaluation | Empathy F1 ≈ 0.78 | Cross-cultural benchmark |
| **MentalChat-16K** | Long-context generation + safety | GPT-4 Empathy ≈ 4.5, Coherence ≈ 0.92 | Combines empathy, reasoning, and safety |
| **Between Help and Harm** | Safety adequacy | GPT-4 F1 ≈ 0.71, Claude ≈ 0.67 | High-risk scenario benchmark |

---

## 📈 Evolution Roadmap

| Stage | Year | Innovation | Representative Datasets |
|:--|:--:|:--|:--|
| **Foundational** | 2021–2022 | Single-turn counseling generation | PsyQA |
| **Empathy Expansion** | 2023 | Empathy stages & emotion annotation | SoulChat |
| **Dialogue Expansion** | 2024 | Multi-turn generation | SMILE / MeChat |
| **Privacy-Preserving** | 2025 | Realistic reconstruction with RMRR | PsyDial |
| **Diagnostic Simulation** | 2025 | Multi-agent DSM-5 reasoning | MDD-5k / MHSD |
| **Cross-Cultural** | 2024–2025 | Multilingual therapy benchmarks | CounseLLMe / HamRaz |
| **Unified Integration** | 2025 | Empathy + reasoning + safety | MentalChat-16K |
| **Safety Evaluation** | 2025 | Crisis handling & adequacy scoring | Between Help and Harm |

---

## 🎯 Research Implication

These datasets together form the **benchmark collection** for LLM-based mental-health dialogue research.  
They define the current **state-of-the-art battlefield**—the standards that upcoming models must **match, evaluate against, and surpass**  
in empathy, diagnostic accuracy, and risk-aware reasoning.

---

## 🤝 Contributing

Contributions are welcome!  
Add new open-source datasets, benchmarks, or evaluation scripts through Pull Requests.

---

## 🔖 Citation

```bibtex
@misc{song2025llm_benchmark_mentalhealth,
  title={Benchmark Collection of LLM-based Mental Health Dialogue Datasets},
  author={Song, Yukai},
  year={2025},
  howpublished={\url{https://github.com/YukaiSong/awesome-mental-health-dialogue-datasets}},
  note={Chronologically organized benchmark collection integrating empathy, diagnosis, and safety evaluation for LLM research.}
}
```

---

## 🧠 Acknowledgement

All credit to the original dataset creators and research teams at  
University of Pittsburgh, UIUC, Zhejiang University, Tsinghua University, ETH Zürich, and other institutions advancing **AI for Mental Health**.

---
