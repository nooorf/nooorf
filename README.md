<!-- ═════════════════════════ HERO ═════════════════════════ -->
<p align="center"><a><img src="hero.svg" width="100%" alt="Noor Fatima — AI / ML Engineer"/></a></p>

<!-- ═════════════════════════ ABOUT ═════════════════════════ -->
<p align="center"><a><img src="about.svg" width="100%" alt="About — Computer Science undergraduate at NUST (CGPA 3.88/4.0, Dean's List 6/6 semesters, merit scholar) building machine learning systems end-to-end, with a co-authored IEEE GLOBECOM 2026 workshop paper"/></a></p>

```yaml
# ── model_card.yaml ──────────────────────────────────────────────
model_id:        noor-fatima
base_model:      BS Computer Science · NUST · CGPA 3.88/4.0 · Dean's List 6/6
pipeline_tag:    ai-ml-engineering
architecture:    deep-learning × systems-engineering
trained_on:      [LLM & RAG systems, MLOps, deep learning, multimodal AI,
                  federated learning, deep reinforcement learning]
eval_results:    IEEE GLOBECOM 2026 Workshop paper (co-author)
inference:       research → prototype → production
serving_layer:   FastAPI · React · TypeScript · WebSockets · Docker
fine_tuning_on:  SpatioArchitect · satellite image + one sentence → 3D house
license:         open-to-opportunities
```

<!-- ═════════════════════════ EXPERIENCE ═════════════════════════ -->
<p align="center"><a><img src="experience.svg" width="100%" alt="Experience: AI/ML Intern at Nexus Technologies (Feb–Apr 2026, RAG-based conversational AI); Frontend Developer at Growthrune (Apr 2025–Feb 2026, led code reviews, real-time agentic AI features, 25% faster page load); Web Designer and Developer at Moboroid (May 2021–Jun 2023, 7+ client projects)"/></a></p>

<!-- ═════════════════════════ RESEARCH ═════════════════════════ -->
<p align="center"><a><img src="research.svg" width="100%" alt="Research and publications: co-author of 'RIS-Assisted Physical Layer Security for PASS-Enabled Backscatter NOMA Systems', IEEE GLOBECOM 2026 Workshop; Student Researcher at IPT Lab, NUST, developing deep reinforcement learning for RIS-assisted backscatter NOMA, raising spatial feasibility from 73.2% to 98.4% across 441 eavesdropper locations; co-author of a DAWN News data analysis of smog in Pakistan"/></a></p>

<!-- ═════════════════════════ TECH STACK ═════════════════════════ -->
<p align="center"><a><img src="stack.svg" width="100%" alt="Tech stack. Languages: Python, C++, SQL, TypeScript, JavaScript, Java. ML and DL: PyTorch, TensorFlow, scikit-learn, XGBoost, MONAI, OpenCV, SHAP, Stable-Baselines3, Gymnasium. LLMs and retrieval: Hugging Face Transformers, Sentence Transformers, Ollama, pgvector. MLOps and cloud: Docker, GitHub Actions, MLflow, Weights and Biases, Evidently, Azure ML, Git, Linux. Data and streaming: pandas, NumPy, SciPy, PostgreSQL, SQLAlchemy, Apache Spark, Apache Kafka, RAPIDS, Delta Lake, GeoPandas. Backend and web: FastAPI, Node.js, WebSockets, React, Material-UI, three.js, Streamlit"/></a></p>

<!-- ═════════════════════════ FEATURED WORK ═════════════════════════ -->
<p align="center"><a><img src="section-featured.svg" width="100%" alt="Featured Work"/></a></p>

<details>
<summary><b>Shelfwise &nbsp;—&nbsp; Conversational, Voice-First Library AI Assistant</b></summary>
<br>

> **A voice-first library assistant with a talking avatar that recommends books by mood, pace and what to leave out — answering only from the library's own shelves, and structurally unable to invent a book.** Hybrid retrieval, an LLM query parser and ID-constrained generation over 5,358 real books, all running locally on an 8 GB laptop with zero paid APIs.

```text
                 Voice  (Whisper + Silero VAD)   ·   or typed text
                                          │
                                          ▼
                  ┌───────────────────────────────────────────────┐
                  │                  QUERY PARSER                 │
                  │       Qwen3-4B (local) · rules fallback       │
                  │     hard constraints · soft prefs · topic     │
                  └───────────────────────┬───────────────────────┘
                                          ▼
                  ┌───────────────────────────────────────────────┐
                  │          FILTER FIRST · ONE SQL QUERY         │
                  │  page limits · on shelf today · "not" facets  │
                  │     → allowed set: a guarantee, not a hint    │
                  └───────────────────────┬───────────────────────┘
              ┌───────────────────────────┼───────────────────────────┐
              ▼                           ▼                           ▼
    ┌───────────────────┐       ┌───────────────────┐       ┌───────────────────┐
    │        BM25       │       │   Dense bge-base  │       │   Exact lookups   │
    │   lexical signal  │       │   meaning · mood  │       │   title · author  │
    └─────────┬─────────┘       └─────────┬─────────┘       └─────────┬─────────┘
              └───────────────────────────┼───────────────────────────┘
                                          ▼
                  ┌───────────────────────────────────────────────┐
                  │          HYBRID FUSION + FACET NUDGES         │
                  │       scored only inside the allowed set      │
                  │             mood · pace · audience            │
                  └───────────────────────┬───────────────────────┘
                                          ▼
                  ┌───────────────────────────────────────────────┐
                  │               GROUNDED NARRATION              │
                  │      LLM may only cite retrieved book IDs     │
                  │        validator checks every sentence        │
                  └───────────────────────┬───────────────────────┘
                                          ▼
    Kokoro streaming TTS  →  VRM avatar lip-sync   ·   web UI chips + inspector

  ┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄
    Offline: 5,358-work catalog → LLM facet tagging · bge embeddings · BM25 index
```

**Highlights**

- **0.687 nDCG@10** on a locked test split — **+14%** over BM25 + dense hybrid search and **+58%** over BM25
- **0% invented books across 150 adversarial cases** (made-up titles, prompt injection) via ID-constrained generation + a sentence validator — versus **21%** for naive RAG and **77%** for an LLM alone
- **Qwen3-4B query parser at 95.0% F1** (98% precision), splitting each request into hard constraints, soft preferences and a topic, with a deterministic rules fallback
- **Facet-based negation** — "without the romance" becomes a filter, not a vector drifting *towards* romance — **halving constraint violations from 62% to 31%** and ranking **2.2× better** on "not" requests
- **Filter-first retrieval** — every constraint compiles into one SQL query, and every retrieval channel scores only inside that allowed set
- **Local voice assistant** — Whisper + Silero VAD in, streaming Kokoro TTS out with barge-in interruption, and a three.js VRM avatar at **59 FPS**, **4 ms median lip-sync offset** and **0.73 s first frame**
- **Research-grade evaluation** — **12,331 graded relevance judgments** with TREC-style pooling, paraphrase-separated dev/test splits to prevent leakage, and paired bootstrap confidence intervals

**Stack** &nbsp; `Python` · `FastAPI` · `WebSockets` · `PostgreSQL + pgvector` · `bge-base` · `BM25` · `Qwen3-4B (Ollama)` · `Whisper` · `Kokoro TTS` · `React` · `three.js`

**Code** &nbsp; [github.com/nooorf/shelfwise](https://github.com/nooorf/shelfwise)

</details>

<details>
<summary><b>Sentinel &nbsp;—&nbsp; Real-Time Fraud Detection & MLOps Platform</b></summary>
<br>

> **An end-to-end ML system for card fraud that watches itself: a sub-10 ms scoring API, drift monitoring that triggers its own retraining, and a model registry that only promotes a candidate once it beats the serving model.** Shipped as a single Docker container with a fraud-operations console.

```text
┌──────────────────────────────────────────────────────────────────────────────────┐
│                         Sentinel  ·  System Architecture                         │
├──────────────────────────┬──────────────────────────┬────────────────────────────┤
│     OFFLINE TRAINING     │     SCORING SERVICE      │      DRIFT MONITORING      │
│                          │                          │                            │
│  time-ordered 60/20/20   │  FastAPI  POST /predict  │  every scored txn logged   │
│  LR · XGBoost · IForest  │    strict Pydantic v2    │  Evidently feature drift   │
│   cost-aware threshold   │  9.7 ms p99 · 260 req/s  │     + prediction drift     │
├──────────────────────────┴──────────────────────────┴────────────────────────────┤
│                 RETRAINING  ·  MODEL REGISTRY  ·  PROMOTION GATE                 │
│                                                                                  │
│      drift alert → background retrain → candidate vs. serving on one split       │
│     promote (hot swap, no restart)  ·  reject (kept for audit)  ·  rollback      │
│             SHA-256 manifest verified before every load or promotion             │
├──────────────────────────────────────────────────────────────────────────────────┤
│      OUTPUT → APPROVE / REVIEW decision · fraud probability · anomaly rank       │
├──────────────────────────────────────────────────────────────────────────────────┤
│    Ops console · MLflow · 42 tests · GitHub Actions CI · one Docker container    │
│      Data: 284,807 card txns · 0.17% fraud      Deploy: Azure ML blue/green      │
└──────────────────────────────────────────────────────────────────────────────────┘
```

**Highlights**

- **9.7 ms p99 end-to-end latency** and **260 requests/s** on a laptop, scoring with XGBoost + Isolation Forest over **284K** real card transactions
- **Precision 0.41 → 0.54** at the same recall target — **46% fewer false alarms**, **31% fewer manual reviews** and **62% lower fraud cost**, measured on a held-out, time-ordered test window
- **Leakage-free by construction** — chronological 60/20/20 split, preprocessing fit on training data only, test set scored exactly once, bootstrap confidence intervals on every metric
- **Built for 0.17% fraud prevalence** — imbalance-aware XGBoost, PR-AUC model selection and a cost-aware decision threshold
- **Self-healing MLOps loop** — Evidently drift monitoring triggers background retraining; a promotion gate checks precision/recall floors and PR-AUC before a zero-downtime hot swap, with one-click rollback
- **Tamper-evident model versioning** — every artifact carries a SHA-256 manifest verified before each load or promotion
- **Production engineering** — 42 automated tests, GitHub Actions CI, MLflow tracking, and Azure ML managed-endpoint deployment scripts with blue/green slots

**Stack** &nbsp; `XGBoost` · `scikit-learn` · `Evidently` · `FastAPI` · `Pydantic v2` · `MLflow` · `Docker` · `GitHub Actions` · `Azure ML`

**Code** &nbsp; [github.com/nooorf/sentinel](https://github.com/nooorf/sentinel)

</details>

<details>
<summary><b>AcademIQ &nbsp;—&nbsp; Evidence-Grounded AI Search Engine</b></summary>
<br>

> **A production-grade Big Data retrieval and question-answering engine that turns dense university policy handbooks into a fast, auditable natural-language knowledge system.** Fuses approximate similarity search, multi-stage ranking, distributed indexing, query mining and grounded LLM synthesis — every answer ships with its source, section and page.

```text
                     ┌───────────────────────────────────┐
                     │      Query Cache · LRU + TTL      │
  User Query ───────►│    thread-safe · < 1 ms on hit    │── hit ──► Answer
                     │    warmed by SON query mining     │
                     └─────────────────┬─────────────────┘
                                       │ miss
            ┌──────────────────────────┼──────────────────────────┐
            ▼                          ▼                          ▼
  ┌───────────────────┐      ┌───────────────────┐      ┌───────────────────┐
  │      TF-IDF       │      │   MinHash + LSH   │      │      SimHash      │
  │   exact lexical   │      │  sub-linear ANN   │      │  near-duplicate   │
  │ precision anchor  │      │ candidate search  │      │  fingerprinting   │
  └─────────┬─────────┘      └─────────┬─────────┘      └─────────┬─────────┘
            │                          │                          │
            └──────────────────────────┼──────────────────────────┘
                                       ▼
                    ┌─────────────────────────────────────┐
                    │    Reciprocal Rank Fusion (RRF)     │
                    │   Re-ranking · Diversity Control    │
                    └──────────────────┬──────────────────┘
                                       ▼
                    ┌─────────────────────────────────────┐
                    │       Grounded LLM Synthesis        │
                    │   evidence-constrained generation   │
                    │         extractive fallback         │
                    └──────────────────┬──────────────────┘
                                       ▼
                   Answer · Source · Section · Page · Latency

  ┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄┄
    Offline: MapReduce-parallel index builds  ·  SON frequent-pattern mining
```

**Highlights**

- **7× faster retrieval** than exact TF-IDF — while **recovering +6 pp precision** through hybrid retrieval and re-ranking
- **54 ms retrieval at 10× corpus scale** — approximate search held firmly in the sub-100 ms regime
- **Reciprocal Rank Fusion** of TF-IDF, MinHash-LSH and SimHash into a single unified relevance ranking
- **Hallucination-resistant LLM synthesis** constrained strictly to retrieved evidence, with an extractive fallback
- **MapReduce-style parallel indexing** for the compute-heavy retrieval indexes
- **SON frequent-pattern mining** to discover recurring query patterns and pre-warm the cache
- **Thread-safe LRU + TTL cache** delivering **< 1 ms** responses on repeated queries

**Stack** &nbsp; `Python` · `scikit-learn` · `MinHash LSH` · `SimHash` · `MapReduce` · `OpenAI API` · `Streamlit`

</details>

<details>
<summary><b>CortexPI &nbsp;—&nbsp; Federated Learning for ICU Sepsis Detection</b></summary>
<br>

> **A real-time, privacy-preserving clinical AI platform that predicts ICU patient deterioration across distributed hospital nodes — without a single patient record ever leaving its source hospital.** Engineered end-to-end across streaming data infrastructure, custom GPU kernels, state-of-the-art sequence models and federated optimization.

```text
┌──────────────────────────────────────────────────────────────────────────────────┐
│                         CortexPI  ·  System Architecture                         │
├──────────────────────────┬──────────────────────────┬────────────────────────────┤
│     STREAM INGESTION     │  GPU STREAM PROCESSING   │     FEDERATED TRAINING     │
│                          │                          │                            │
│  Apache Kafka            │  RAPIDS cuDF + Spark     │  FedAvg + Differential     │
│  exactly-once semantics  │  Structured Streaming    │  Privacy · 5 hospital      │
│  live vitals + ECG feeds │  Delta Lake lakehouse    │  nodes · torchrun 2×T4     │
├──────────────────────────┴──────────────────────────┴────────────────────────────┤
│                                DEEP LEARNING CORE                                │
│                                                                                  │
│      Mamba SSM ECG Encoder  ·  GRU-D Vitals Encoder  ·  Graph Attention Net      │
│         Custom Triton Pan-Tompkins GPU Kernel  ·  EWC Continual Learning         │
│               Conformal Prediction  ·  3 Clinical Prediction Heads               │
├──────────────────────────────────────────────────────────────────────────────────┤
│      OUTPUT → real-time deterioration risk + calibrated uncertainty bounds       │
├──────────────────────────────────────────────────────────────────────────────────┤
│  Data: PhysioNet 2012 · PTB-XL        Compute: Apple M2 Pro · Kaggle dual-T4     │
└──────────────────────────────────────────────────────────────────────────────────┘
```

**Highlights**

- **Mamba state-space ECG encoder** for long-range cardiac sequence modeling — outperforms LSTM baselines on irregular clinical time series
- **GRU-D vitals encoder** with learned missingness decay, built for the extreme sparsity of real ICU data
- **Custom Triton GPU kernel** running Pan-Tompkins QRS detection fully on-GPU — ECG preprocessing benchmarked at **2,400 ms → 31 ms (77× speedup)**
- **FedAvg + Differential Privacy** across 5 hospital nodes with formal (ε, δ) privacy guarantees
- **Graph Attention Network** modeling relational structure across clinical signals, driving **3 clinical prediction heads**
- **EWC continual learning** that defends against catastrophic forgetting as patient populations drift
- **Conformal prediction** wrapping every risk score in calibrated, distribution-free uncertainty bounds
- **2-GPU pipeline parallelism** via `torchrun` on dual-T4 infrastructure, fed by an exactly-once Kafka → Spark → Delta Lake stream
- **Distributed GPU inference** with parallel execution, targeting **sub-100 ms per-patient latency** across the streaming architecture

**Stack** &nbsp; `PyTorch` · `Mamba SSM` · `Triton` · `RAPIDS cuDF` · `Apache Spark` · `Apache Kafka` · `Delta Lake` · `Federated Learning`

</details>

<details>
<summary><b>3D Brain Tumor Segmentation &nbsp;—&nbsp; Multi-Modal MRI · MONAI 3D U-Net</b></summary>
<br>

> **A volumetric deep-learning pipeline that fuses four complementary MRI sequences — T1, T1ce, T2 and FLAIR — to deliver voxel-precise, multi-class brain tumor segmentation with a compact MONAI 3D U-Net.**

```text
    ┌───────────────────────────────────┐
    │   BraTS 2020 · Multi-Modal MRI    │
    │   T1  ·  T1ce  ·  T2  ·  FLAIR    │
    └─────────────────┬─────────────────┘
                      │  4-channel volumetric fusion
                      ▼
    ┌───────────────────────────────────┐
    │         3D Preprocessing          │
    │ Intensity norm · Label remapping  │
    │ Foreground-biased patch sampling  │
    └─────────────────┬─────────────────┘
                      │  96³ voxel patches
                      ▼
    ┌───────────────────────────────────┐
    │          MONAI 3D U-Net           │
    │         4.8 M parameters          │
    │         Dice + Focal loss         │
    └─────────────────┬─────────────────┘
                      │  sliding-window inference
                      ▼
    ┌───────────────────────────────────┐
    │     4-Class Voxel Prediction      │
    │  Background · NCR/NET · ED · ET   │
    └─────────────────┬─────────────────┘
                      │  patient-level held-out split
                      ▼
    ┌───────────────────────────────────┐
    │  Quantitative + Qualitative Eval  │
    │      55 validation patients       │
    └───────────────────────────────────┘
```

**Highlights**

- **0.6479 mean validation Dice** across **55 held-out patients**
- **0.7652 Dice on Enhancing Tumor** — the clinically critical sub-region and the model's strongest class
- **4-modal 3D MRI fusion** into a single volumetric input for voxel-level reasoning
- **Compact 4.8 M-parameter 3D U-Net** trained with a hybrid **Dice + Focal loss** to defeat extreme class imbalance
- **Foreground-biased 96³ patch sampling** + **sliding-window inference** for full-volume prediction
- **Leak-proof evaluation** — strict patient-level splits, independent validation, fully tracked in W&B

**Stack** &nbsp; `PyTorch` · `MONAI` · `3D U-Net` · `BraTS 2020` · `Weights & Biases`

**Code** &nbsp; [github.com/nooorf/brain-tumor-segmentation](https://github.com/nooorf/brain-tumor-segmentation)

</details>

<details>
<summary><b>London Crime Predictive Intelligence &nbsp;—&nbsp; Geospatial Risk Engine</b></summary>
<br>

> **A city-scale geospatial intelligence platform that forecasts crime risk across every London neighbourhood (LSOA)** — fusing census, socio-economic, POI and temporal signals into an ensemble ML engine, explained with SHAP and rendered as an interactive **3D digital twin** with live what-if policy simulation.

```text
                 ┌───────────────────────────────────────┐
                 │           DATA FUSION LAYER           │
                 │  Census · Crime Records · Geography   │
                 │   POIs · Socio-economic · Temporal    │
                 └───────────────────┬───────────────────┘
                                     ▼
                 ┌───────────────────────────────────────┐
                 │       FEATURE ENGINEERING & EDA       │
                 │     LSOA-level joins · Imputation     │
                 │      Spatial + temporal features      │
                 └───────────────────┬───────────────────┘
                  ┌──────────────────┴──────────────────┐
                  ▼                                     ▼
    ┌───────────────────────────┐         ┌───────────────────────────┐
    │      CLASSIFICATION       │         │        REGRESSION         │
    │  XGBoost · Random Forest  │         │  Random Forest Regressor  │
    │   Low / Med / High risk   │         │   Continuous risk score   │
    │       83% accuracy        │         │          0.95 R²          │
    └─────────────┬─────────────┘         └─────────────┬─────────────┘
                  └──────────────────┬──────────────────┘
                                     ▼
                 ┌───────────────────────────────────────┐
                 │            EXPLAINABLE AI             │
                 │    SHAP per-prediction attribution    │
                 └───────────────────┬───────────────────┘
                                     ▼
                 ┌───────────────────────────────────────┐
                 │    INTERACTIVE INTELLIGENCE LAYER     │
                 │      3D Geospatial Digital Twin       │
                 │      What-If Scenario Simulation      │
                 │      Before / After Risk Deltas       │
                 └───────────────────────────────────────┘
```

**Highlights**

- **83% accuracy** classifying Low / Medium / High risk with XGBoost
- **0.95 R²** on continuous risk-score regression with a Random Forest ensemble
- **3D geospatial digital twin** of London's LSOA geography built in PyDeck
- **What-if scenario engine** — perturb socio-economic levers and quantify the before/after risk delta in real time
- **SHAP explainability** surfacing the exact drivers behind every individual prediction
- **Decision-grade Streamlit dashboard** unifying 3D maps, model switching, simulation and explanations

**Stack** &nbsp; `XGBoost` · `scikit-learn` · `SHAP` · `GeoPandas` · `PyDeck` · `Plotly` · `Streamlit`

</details>

<details>
<summary><b>SpatioArchitect &nbsp;—&nbsp; Satellite Image + One Sentence → Walkable 3D House</b></summary>
<br>

**In progress &nbsp;·&nbsp; Final Year Project &nbsp;·&nbsp; 3-person team**

> **Give it a satellite image of a real plot and one sentence — *“3-bedroom modern house with 2 bathrooms”* — and it generates a boundary-compliant, fully furnished 3D house you can walk through and edit in the browser.** Neural networks do what learning is best at — reading imagery and proposing architectural layouts — while deterministic, oracle-checked geometry owns everything a user can stand inside.

```text
     Satellite image of the plot               "3-bed modern house, 2 baths"
                 ▼                                          ▼
  ┌─────────────────────────────┐            ┌─────────────────────────────┐
  │         1 · VISION          │            │      2 · BRIEF → GRAPH      │
  │   SAM 2 plot segmentation   │            │ program + feasibility gate  │
  │ GSD metric scale · setback  │            │    bubble-diagram prior     │
  └──────────────┬──────────────┘            └──────────────┬──────────────┘
                 └────────────────────┬─────────────────────┘
                                      ▼
                   ┌─────────────────────────────────────┐
                   │    3 · BOUNDARY-GUIDED DIFFUSION    │
                   │   HouseDiffusion + training-free    │
                   │      clean-estimate projection      │
                   └──────────────────┬──────────────────┘
                                      ▼
                   ┌─────────────────────────────────────┐
                   │    4 · CONSTRUCTION + FURNISHING    │
                   │    3D shell · fixture manifests     │
                   │ SAT collision · circulation oracle  │
                   └──────────────────┬──────────────────┘
                                      ▼
                   ┌─────────────────────────────────────┐
                   │      5 · WALKTHROUGH + EDITOR       │
                   │       first-person navigation       │
                   │     every edit oracle-validated     │
                   └──────────────────┬──────────────────┘
                                      ▼
               Furnished · walkable · editable 3D house  →  glTF
```

**Highlights**

- **Training-free boundary-guided diffusion** — projects HouseDiffusion's clean estimate onto boundary-compliant layouts *inside* the sampling loop, so plans fit real, non-convex parcels with zero retraining
- **Zero-shot plot extraction with SAM 2** — Web-Mercator GSD calibration turns map pixels into real metres, with construction setbacks applied automatically
- **Semantically complete interiors** — declarative fixture manifests (every bathroom gets its toilet, sink and tub/shower), plumbing-aware wet-wall anchoring and exact SAT collision checks
- **Provable navigability** — a morphological circulation oracle guarantees a ≥ 60 cm path to every door and fixture
- **One geometric oracle** shared by generation, editing and evaluation — the house can never be edited into an invalid state
- **90.4% boundary IoU** already achieved by the proof of concept on rectangular plots
- **Research-grade evaluation** — 100-plot stratified benchmark against 4 baselines, paired Wilcoxon + Holm statistics, ablations and a user study

**My focus** &nbsp; Built together as a team; my core area is Deep Learning & Mathematical Modelling.

**Stack** &nbsp; `PyTorch` · `HouseDiffusion` · `SAM 2` · `Shapely` · `trimesh` · `glTF` · `FastAPI` · `React` · `three.js` · `Docker`

</details>

<br>

<!-- ═════════════════════════ EXPERTISE ═════════════════════════ -->
<p align="center"><a><img src="expertise.svg" width="100%" alt="Core expertise. Modeling: deep neural architectures, transformers, sequence models, generative and diffusion models, deep reinforcement learning, classical ML. ML Systems: end-to-end pipelines, RAG and hybrid retrieval, distributed and federated training, real-time inference APIs, data engineering, MLOps. Reliable AI: rigorous evaluation, grounded LLM generation, uncertainty quantification, interpretability, privacy-preserving ML, efficient AI"/></a></p>

<!-- ═════════════════════════ EXPLORING ═════════════════════════ -->
<p align="center"><a><img src="exploring.svg" width="100%" alt="Currently exploring: generative AI for design, multimodal foundation models, efficient deep learning, reinforcement learning, distributed and federated learning, modern transformer architectures"/></a></p>

<!-- ═════════════════════════ ANALYTICS ═════════════════════════ -->
<p align="center"><a><img src="section-analytics.svg" width="100%" alt="GitHub Analytics"/></a></p>

<p align="center">
  <a><img height="165" src="https://github-readme-stats.vercel.app/api?username=nooorf&show_icons=true&include_all_commits=true&count_private=true&hide_border=true&bg_color=00000000&title_color=22D3EE&icon_color=8B5CF6&text_color=94A3B8&rank_icon=github" alt="GitHub stats"/></a>
  <a><img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=nooorf&layout=compact&langs_count=6&hide_border=true&bg_color=00000000&title_color=22D3EE&text_color=94A3B8" alt="Top languages"/></a>
</p>
<p align="center">
  <a><img src="https://streak-stats.demolab.com?user=nooorf&hide_border=true&background=00000000&ring=22D3EE&fire=8B5CF6&currStreakLabel=22D3EE&sideLabels=94A3B8&dates=64748B&currStreakNum=F8FAFC&sideNums=F8FAFC&stroke=1E293B" alt="GitHub streak"/></a>
</p>

<!-- ═════════════════════════ FOOTER ═════════════════════════ -->
<p align="center">
  <a href="https://portfolio-nooorfs-projects.vercel.app/"><img src="btn-portfolio.svg" height="50" alt="Portfolio"/></a>
  <a href="https://www.linkedin.com/in/noorfatima4428/"><img src="btn-linkedin.svg" height="50" alt="LinkedIn"/></a>
  <a href="mailto:nfatima.bscs23seecs@seecs.edu.pk"><img src="btn-email.svg" height="50" alt="Email"/></a>
</p>

<p align="center"><a><img src="footer.svg" width="100%" alt="Noor Fatima · research-grade models, production-grade systems"/></a></p>
