# GastroZO — AI-assisted Stool Characterization & Gut Risk Triage  
**AI x MedTech: Startup Hackathon & Cohort 2025**

GastroZO is a research-oriented AI clinical decision support (CDS) prototype designed to **standardize stool characterization** using patient-provided stool images and symptom context. It outputs a **Bristol stool type prediction**, visual indicators (color/abnormality flags), and an interpretable **triage risk level (Green / Amber / Red)**. The system further generates a **clinician-ready structured summary** to improve telemedicine decision-making, reduce subjective reporting errors, and support safer follow-up monitoring.

Unlike general “gut health” trackers, GastroZO is built with a **clinical workflow-first design**: data acquisition → quality checks → AI inference → risk scoring → clinician summary → feedback loop. The focus is not to replace clinicians, but to **assist faster triage and escalation** while keeping safety guardrails and privacy-by-design as first-class requirements.

---

## Table of Contents
1. [Problem Statement](#problem-statement)
2. [Why Existing Solutions Fail](#why-existing-solutions-fail)
3. [Our Solution: GastroZO](#our-solution-gastrozo)
4. [Key Innovations](#key-innovations)
5. [Hackathon Theme Alignment](#hackathon-theme-alignment)
6. [End-to-End Workflow](#end-to-end-workflow)
7. [System Architecture](#system-architecture)
8. [AI Methodology](#ai-methodology)
9. [Dataset Strategy & Preprocessing](#dataset-strategy--preprocessing)
10. [Risk Stratification Logic](#risk-stratification-logic)
11. [MVP Prototype (Patient + Clinician Flows)](#mvp-prototype-patient--clinician-flows)
12. [Clinical Safety, Ethics & Privacy](#clinical-safety-ethics--privacy)
13. [Results & Observations](#results--observations)
14. [Evaluation Tables](#evaluation-tables)
15. [Roadmap & Pilot Plan](#roadmap--pilot-plan)
16. [Business Model](#business-model)
17. [Repository Structure](#repository-structure)
18. [How to Run (Prototype)](#how-to-run-prototype)
19. [Future Enhancements](#future-enhancements)
20. [Disclaimer](#disclaimer)
21. [License](#license)

---

## Problem Statement

Gastrointestinal symptoms such as diarrhea, constipation, abdominal discomfort, irregular bowel movement frequency, and suspected gut infections contribute significantly to outpatient consultations and telemedicine follow-ups. However, **remote gut-health triage is still unreliable**, primarily due to the absence of standardized stool reporting in home environments.

In typical teleconsultation workflows, stool information is captured through subjective patient descriptions such as “loose”, “hard”, or “watery”. This creates **clinical uncertainty**, increases repeated questioning, delays escalation decisions, and reduces the quality of remote monitoring. Furthermore, potential red flags such as suspected bleeding indicators or severe dehydration risk are often not reliably communicated early.

### Core Challenges (Clinical + Operational)
- **Subjective and inconsistent stool descriptions** across patients  
- **Low compliance** with manual stool diaries and symptom tracking  
- **Lack of clinical standardization** in most telemedicine platforms  
- **Delayed escalation** when red flags are not highlighted early  
- **High workload** for clinicians due to repetitive patient interrogation  

### Why It Matters
Even when a case is non-emergency, lack of structure leads to:
- avoidable patient anxiety  
- unnecessary repeated consultations  
- delayed investigations (tests/imaging)  
- reduced trust in telemedicine outcomes  

---

## Why Existing Solutions Fail

Current tools fail in gut triage primarily because they are not designed as clinician-grade decision support systems.

### Gaps in Current Practice
- Most wellness apps focus on **general health tracking**, not risk triage.
- Stool reports are rarely standardized into interpretable scales (e.g., Bristol).
- There is no robust **image quality gating**, so inaccurate inputs dominate outcomes.
- Many systems lack **explainability cues** for clinician trust and adoption.
- Almost no solution integrates a **triage-ready summary** for a doctor dashboard.

## Limitation visualization

![Diagram](IMG/Problem_Statement.png)
---

## Our Solution: GastroZO

GastroZO standardizes stool reporting and converts it into **decision-ready outputs** for telemedicine and OPD-style fast triage. The platform combines:

- **Image-based stool characterization**
- **Symptom + history context fusion**
- **Risk stratification (Green/Amber/Red)**
- **Clinician-ready structured summary**
- **Safety controls for uncertain predictions**

In simple terms:

> GastroZO transforms an unstructured stool image + symptoms into a structured clinical triage report.

## Proposed Solution Understanding Visulaization

![Diagram](IMG/Venn_Representation.png)

## Pipeline Workflow Automation Diagram

![Diagram](IMG/Visualization.png)
---

## Key Innovations

### 1) Standardized Stool Characterization
GastroZO outputs a standardized stool profile aligned with clinical communication patterns:
- Bristol stool type (1–7)
- stool color class
- abnormality suspicion flags (mucus/blood cues)

### 2) Multi-Modal Risk Stratification
The system does not rely on images alone. It combines:
- stool appearance patterns  
- symptom severity and duration  
- red-flag symptoms  
to produce a risk level aligned with triage decision-making.

### 3) Clinician-First Summary Generation
Instead of providing just a “prediction”, GastroZO produces:
- a structured overview for rapid decision-making  
- a triage recommendation output  
- confidence score + cues to reduce ambiguity  

### 4) Safety Guardrails + Quality Gating
To prevent unsafe outputs:
- low-quality images are flagged/rejected
- uncertain predictions trigger conservative guidance
- red-flag symptom patterns trigger escalation suggestions

### 5) Privacy-by-Design
- explicit consent workflow  
- minimal data capture policy  
- metadata stripping (EXIF removal)  
- secure storage + controlled access  

---

## Hackathon Theme Alignment

✅ **Primary Category: Telemedicine & AI Clinical Decision Support**  
GastroZO is built specifically for remote assessment + clinician decision support.

Secondary alignment:
- **AI in HealthTech Innovation**
- **Health IT Systems & Healthcare Data Privacy**

---

## End-to-End Workflow

The GastroZO workflow is designed for fast deployment and clinical usability:

1. **Patient Input**
   - stool image capture or upload  
   - structured symptom form  
   - duration + basic context (optional vitals)

2. **Quality Gate + Preprocessing**
   - blur detection  
   - illumination and noise checks  
   - normalization + resizing  
   - privacy filtering (metadata removal)

3. **AI Inference**
   - Bristol scale classification  
   - stool feature extraction  
   - color + abnormality flags  

4. **Risk Stratification**
   - risk grouping: Green / Amber / Red  
   - confidence scoring and safety thresholds  

5. **Clinician Summary**
   - short structured clinical report  
   - “next-step” recommendation  
   - high-risk alert cues  

6. **Clinician Feedback Loop (Optional)**
   - clinician validation labels  
   - continuous improvement readiness  

---

## System Architecture

GastroZO uses a modular architecture enabling expansion from MVP to pilot-stage deployment.

### Architecture Blocks
- **Patient Interface (Mobile/Web)**
  - capture/upload stool image  
  - symptom data collection  
  - consent and disclaimers  

- **AI Processing Layer**
  - quality control gate  
  - preprocessing pipeline  
  - multi-task classification model  

- **Risk Engine**
  - rule-assisted scoring  
  - confidence-based escalation  
  - red flag detection  

- **Clinician Dashboard**
  - triage queue (Green/Amber/Red tags)  
  - structured summaries  
  - action logging  

- **Secure Storage**
  - encrypted data storage  
  - access control  
  - audit logs  

### Architecture Diagram

![Diagram](IMG/Architecture.png)

### Architecture Pipeline Diagram

![Diagram](IMG/Architecture_pipeline.png)

**Descriptive Note:**  
This architecture illustrates the complete patient-to-clinician workflow. It highlights data acquisition, preprocessing and gating, AI inference, triage scoring, clinician output generation, and a feedback loop for calibration and clinical validation.

---

## AI Methodology

GastroZO follows a multi-task learning approach optimized for clinical interpretability.

### Model Approach (High-Level)
- **Image Encoder**
  - CNN / Vision Transformer backbone  
  - outputs robust feature embeddings  

- **Symptom Encoder**
  - lightweight tabular model (MLP)  
  - encodes symptom features: duration, frequency, pain level, dehydration indicators  

- **Fusion Layer**
  - concatenation/attention fusion  
  - creates unified patient state representation  

- **Prediction Heads**
  1. Bristol score classification (1–7)
  2. Color class prediction  
  3. Abnormality flag detection  
  4. Risk stratification output (Green/Amber/Red)

### AI Methodology Diagram

![Diagram](IMG/Methodological.png)

**Descriptive Note:**  
This diagram demonstrates the multi-modal fusion pipeline and how the model’s outputs feed into the risk engine and clinician decision support summary generation.

---

## Dataset Strategy & Preprocessing

A strong preprocessing strategy ensures stable and reliable inference even in home environments.

### Dataset Strategy (Prototype to Clinical)
- **Phase 1: Prototype Development**
  - controlled sample images  
  - synthetic scenarios and demonstrations  
  - focus on system pipeline correctness  

- **Phase 2: Robustness & Generalization**
  - diverse lighting conditions  
  - device variations (camera quality differences)  
  - augmentation and quality gating improvements  

- **Phase 3: Clinical Validation**
  - clinician consensus labeling  
  - calibration and threshold tuning  
  - bias monitoring and reporting  

### Preprocessing Pipeline
- resize and normalize  
- blur/noise detection  
- illumination correction  
- cropping/ROI normalization (optional)  
- EXIF removal  
- quality gating based on threshold score  

### Dataset & Preprocessing Diagram

![Diagram](IMG/Dataset_strategy.png)

**Descriptive Note:**  
This pipeline figure outlines how GastroZO prepares images for inference and training. It ensures low-quality samples are filtered, improving reliability and reducing unsafe outputs.

---

## Risk Stratification Logic

GastroZO produces a triage-level decision support output, not a diagnosis.

### Risk Levels
- **Green:** Routine monitoring likely sufficient  
- **Amber:** Consultation recommended (non-emergency but needs review)  
- **Red:** Urgent attention suggested, possible escalation required  

### High-Level Risk Engine Inputs
- Bristol stool type (extremes more concerning)
- color class abnormalities (black/red suspected)
- symptom severity and duration
- red flag responses (dehydration, fever, persistent blood suspicion)
- confidence score

### Risk Logic Table (Simplified)
| Input Indicators | Risk | Suggested Next Step |
|---|---|---|
| normal patterns + mild symptoms | Green | home monitoring + hydration guidance |
| moderate abnormalities or prolonged symptoms | Amber | teleconsult + tests if needed |
| red-flag cues or high-risk prediction | Red | urgent referral / emergency guidance |

---

## MVP Prototype (Patient + Clinician Flows)

The MVP focuses on real usability and hackathon-level demo readiness.

### Patient-Side MVP
- Stool image capture/upload
- Symptom collection (structured)
- Output display:
  - stool type + indicators
  - risk level tag
  - safe next steps (non-diagnostic)

### Clinician-Side MVP
- triage queue with risk tags
- structured summary view
- confidence score + reasoning cues
- option to confirm/correct label

### MVP Application UI Flow Diagram

![Diagram](IMG/Interface.png)

**Descriptive Note:**  
This illustration shows the end-user application workflow from patient capture to AI results to clinician triage queue, ensuring a complete demo-ready product flow.

---

## Clinical Safety, Ethics & Privacy

GastroZO prioritizes patient safety and responsible AI use.

### Clinical Safety Controls
- image quality rejection to prevent incorrect inference  
- confidence thresholding for uncertain outputs  
- explicit messaging: “not a diagnosis”  
- red-flag escalation guidance for urgent patterns  
- clinician-in-the-loop design for final decision authority  

### Privacy Controls
- consent-first onboarding  
- minimal data capture and retention policy  
- encryption at rest + in transit (pilot stage)  
- role-based access control for clinician dashboard  
- audit logs for traceability and accountability  


**Descriptive Note:**  
This diagram describes the layered security, ethical AI, and governance controls that ensure GastroZO remains assistive, transparent, and privacy-preserving.

---

## Results & Observations

### Prototype-Stage Outcome Summary
During hackathon-stage testing with controlled sample scenarios, the system demonstrated promising outcomes:

- GastroZO improved stool reporting consistency by converting subjective descriptors into standardized outputs.
- Triage categorization reduced ambiguity and supported faster teleconsultation decision-making.
- Quality gating prevented several unreliable inferences from blurred/low-light samples.
- Risk stratification was most effective when combined with symptom-based red-flag indicators.
- The clinician summary improved interpretability and reduced follow-up questioning overhead.

> **Note:** These are prototype-stage observations and require clinical validation before real-world deployment.

### Result Snapshot Table (Prototype Template)
| Component | Observation | Outcome |
|---|---|---|
| Image QC Gate | rejected low-light images | reduced unsafe outputs |
| Stool Type Prediction | stable on clean inputs | improved standardization |
| Risk Engine | strong with symptom fusion | better triage signal |
| Clinician Summary | faster review | reduced cognitive load |
| Workflow Completion | smooth patient→doctor path | demo-ready MVP |

---

## Evaluation Tables

### Table 1 — Output Definitions

| Output | Type | Example Values | Clinical Use |
|---|---|---|---|
| Bristol Type | Multi-class | 1–7 | standardized consistency |
| Color Class | Multi-class | normal/pale/dark/red-suspected | abnormality cue |
| Abnormality Flag | Binary | mucus/blood suspected | risk assistance |
| Risk Level | Multi-class | Green/Amber/Red | triage prioritization |
| Confidence | Continuous | 0.00–1.00 | safety gating |

### Table 2 — Recommended Metrics (Clinical + ML)

| Metric | Why It Matters | Priority |
|---|---|---|
| Recall (Red Risk) | avoid missing urgent cases | Highest |
| Precision (Red Risk) | reduce false alarms | High |
| Macro F1 | balanced performance | Medium |
| Calibration | confidence reliability | High |
| Confusion Matrix | failure analysis | High |

### Table 3 — Clinical Validation Plan (Pilot Template)

| Validation Step | Method | Expected Output |
|---|---|---|
| Clinician label review | consensus labeling | gold standard dataset |
| Threshold tuning | calibration curve | safe triage cutoffs |
| Workflow testing | OPD/telemedicine run | usability proof |
| Monitoring | drift + OOD checks | reliability tracking |

---

## Roadmap & Pilot Plan

### Hackathon MVP (0–2 Weeks)
- UI + inference pipeline  
- Bristol + risk engine integration  
- structured summary output  

### Cohort MVP Build (Month 1–2)
- clinician dashboard enhancement  
- data logging + audit trail  
- stronger preprocessing and thresholds  

### Clinical Validation (Month 3–4)
- clinician consensus labeling  
- evaluation + calibration  
- bias analysis and improvements  

### Pilot Deployment (Month 5–6)
- OPD/telemedicine pilot integration  
- real adoption metrics  
- investor readiness outcomes  

---

## Business Model and Roapmap Visulization architecture

![Diagram](IMG/Roadmap.png)

GastroZO is positioned as a scalable clinical decision-support layer for remote gut-health triage.

### Target Customers
- Telemedicine platforms  
- OPD-based clinics  
- Hospitals managing high-volume follow-ups  

### Revenue Model
- SaaS subscription per clinic/hospital  
- per-provider licensing  
- paid pilot + enterprise expansion  

### Deployment Advantage
- modular API-based architecture  
- clinician-friendly structured outputs  
- safety + privacy by design  

---

