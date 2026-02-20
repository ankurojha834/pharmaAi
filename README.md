# 🧬 PharmaGuard
### AI-Powered Drug Safety from Your DNA

> **RIFT 2026 Hackathon · HealthTech Track · Problem Statement 2 — Precision Medicine**

---

## 🚨 The Problem

**Every year, 100,000+ Americans die from adverse drug reactions.**

Most of these deaths are **preventable**. The cause? Doctors prescribe the same drug at the same dose to every patient — but our genes are different. Some people metabolize drugs too fast. Some too slow. The result: the right drug becomes toxic or useless depending on who takes it.

> *Codeine is safe for most people. For someone with a CYP2D6 gene mutation, it converts to a lethal dose of morphine.*

---

## 💡 Our Solution — PharmaGuard

**Upload a patient's genetic file. Select a drug. Get an instant AI-powered safety report.**

PharmaGuard reads a patient's **VCF (genomic data) file**, identifies critical gene variants, and predicts exactly how that patient will respond to a specific drug — with a full clinical explanation powered by **Google Gemini AI**.

```
Patient DNA (VCF file)  +  Drug Name  →  Safe / Adjust Dose / Toxic / Ineffective
```

---

## 🎯 What It Does — In Plain English

| Step | What Happens |
|------|-------------|
| 1️⃣ | Doctor uploads patient's genetic file (VCF format) |
| 2️⃣ | PharmaGuard scans 6 critical pharmacogenes |
| 3️⃣ | AI identifies how the patient metabolizes the drug |
| 4️⃣ | System predicts: Safe / Adjust Dosage / Toxic / Ineffective |
| 5️⃣ | Generates full clinical report with dosing recommendations |

---

## 🌐 Live Demo

### 👉 [https://pharmaguard.onrender.com](https://pharmaguard.onrender.com)

## 🎥 Demo Video

### 👉 [Watch on LinkedIn](https://linkedin.com/YOUR_VIDEO_LINK)
`#RIFT2026` `#PharmaGuard` `#Pharmacogenomics` `#AIinHealthcare`

---

## ⚡ Try It In 3 Steps

```
1. Open the live URL above
2. Click "Load Sample Patient VCF" (no file upload needed to demo!)
3. Select CODEINE → Click "Analyze with AI"
```

**Result in ~10 seconds:**
- 🔴 TOXIC — Critical (for CYP2D6 Poor Metabolizer patient)
- Full explanation: gene variant → biological mechanism → clinical risk
- Dosing recommendation + alternative drugs suggested
- Downloadable structured JSON output

---

## 🧬 The Science Behind It

PharmaGuard analyzes **6 genes** that control how your body processes drugs:

| Gene | Controls | Example Risk |
|------|----------|-------------|
| **CYP2D6** | Codeine, antidepressants | Ultrarapid = fatal morphine overdose |
| **CYP2C19** | Clopidogrel, PPIs | Poor metabolizer = blood clot risk |
| **CYP2C9** | Warfarin, NSAIDs | Poor metabolizer = bleeding risk |
| **SLCO1B1** | Statins (Simvastatin) | Variant = muscle breakdown |
| **TPMT** | Azathioprine | Deficiency = bone marrow failure |
| **DPYD** | Fluorouracil (chemo) | Deficiency = fatal toxicity |

All recommendations follow **CPIC Level A guidelines** — the gold standard in precision medicine.

---

## 🏗️ Architecture

```
┌──────────────────────────────────────────┐
│             BROWSER (UI)                 │
│  Drag & Drop VCF → Select Drug → Results │
└─────────────────┬────────────────────────┘
                  │ POST /api/ai
┌─────────────────▼────────────────────────┐
│         NODE.JS BACKEND (server.js)      │
│  • Receives full VCF + drug name         │
│  • Sends to AI with clinical prompt      │
│  • Auto-retries on rate limits           │
│  • Supports 3 AI providers               │
└──────────┬──────────┬───────────┬────────┘
           ▼          ▼           ▼
     Google Gemini  Groq AI   OpenRouter
     (primary)    (fallback) (fallback)
```

**Key design:** The entire raw VCF is sent to the AI — it reads real variants and generates real personalized analysis, not generic canned responses.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML / CSS / Vanilla JS |
| Backend | Node.js + Express |
| Primary AI | Google Gemini 2.0 Flash |
| Fallback AI | Groq (Llama 3.3 70B) — 14,400 free req/day |
| Fallback AI | OpenRouter (Mistral / DeepSeek — free) |
| Hosting | Render.com (free tier) |
| Standards | CPIC Guidelines + VCF v4.2 |

---

## 📤 JSON Output — Exact Schema Match

```json
{
  "patient_id": "PATIENT_4821",
  "drug": "CODEINE",
  "timestamp": "2026-02-19T10:00:00.000Z",
  "risk_assessment": {
    "risk_label": "Toxic",
    "confidence_score": 0.95,
    "severity": "critical"
  },
  "pharmacogenomic_profile": {
    "primary_gene": "CYP2D6",
    "diplotype": "*4/*4",
    "phenotype": "PM",
    "phenotype_label": "Poor Metabolizer",
    "detected_variants": [
      { "rsid": "rs3892097", "chrom": "chr22", "pos": "42526694",
        "ref": "G", "alt": "A", "gene": "CYP2D6", "star_allele": "*4", "impact": "HIGH" }
    ]
  },
  "clinical_recommendation": {
    "summary": "CONTRAINDICATED — Avoid codeine. Use morphine or non-opioid alternatives.",
    "cpic_guideline": "https://cpicpgx.org/guidelines/codeine/",
    "alternative_drugs": ["morphine", "oxycodone", "hydromorphone"],
    "monitoring_required": true
  },
  "llm_generated_explanation": {
    "summary": "Patient carries CYP2D6 *4/*4 (rs3892097), resulting in Poor Metabolizer phenotype with absent enzymatic activity...",
    "biological_mechanism": "CYP2D6 *4 splice site mutation eliminates functional enzyme production...",
    "clinical_context": "CPIC Level A: avoid codeine in CYP2D6 poor metabolizers.",
    "model": "gemini-2.0-flash"
  },
  "quality_metrics": {
    "vcf_parsing_success": true,
    "variants_detected": 2,
    "gene_coverage": "CYP2D6",
    "diplotype_confidence": "high"
  }
}
```

---

## 🧪 Sample Test Files (in `/samples/`)

| File | Genetic Profile | Expected Result |
|------|----------------|----------------|
| `patient_high_risk.vcf` | CYP2D6\*4/\*4, TPMT\*3A, DPYD\*2A | 🔴 Toxic / Contraindicated |
| `patient_normal.vcf` | All \*1/\*1 reference alleles | 🟢 Safe / Standard dosing |
| `patient_intermediate.vcf` | Mixed CYP2D6\*4/\*1, SLCO1B1\*5 | 🟡 Adjust Dosage |

---

## 🚀 Local Setup

```bash
# 1. Clone the repo
git clone https://github.com/ankurojha834/pharmaguard.git
cd pharmaguard

# 2. Install dependencies
npm install

# 3. Add API keys — copy .env.example to .env and fill in:
#    GEMINI_API_KEY=AIzaSy...    → aistudio.google.com/app/apikey (free)
#    GROQ_API_KEY=gsk_...        → console.groq.com (free, generous)

# 4. Start server
npm start

# 5. Open in browser
# http://localhost:3001
```

---

## 🔌 API Reference

### `POST /api/ai` — Main AI endpoint
```json
Request:  { "provider": "gemini", "model": "gemini-2.0-flash", "prompt": "..." }
Response: { "text": "[ ... JSON analysis results ... ]" }
```

### `GET /health` — Server status
```json
{ "status": "ok", "providers": { "gemini": true, "groq": true, "openrouter": false } }
```

---

## 📁 Project Structure

```
pharmaguard/
├── public/
│   └── index.html              ← Full frontend UI
├── samples/
│   ├── patient_high_risk.vcf
│   ├── patient_normal.vcf
│   └── patient_intermediate.vcf
├── server.js                   ← Backend + AI proxy
├── package.json
├── render.yaml                 ← One-click Render.com deployment
├── .env.example                ← API key template
└── README.md
```

---

## 👥 Team

| Name | Role |
|------|------|
| **Ankur Ojha** | Full Stack + AI Integration |
| **[Team Member 2]** | [Role] |

---

## ✅ Submission Checklist

- [x] Live deployed web application
- [x] Public GitHub repository
- [x] VCF file upload with drag-and-drop
- [x] JSON output matches exact required schema
- [x] All 6 pharmacogenes covered
- [x] 6 drugs supported + custom drug input
- [x] LLM explanations with variant citations
- [x] CPIC-aligned dosing recommendations
- [x] 3 sample VCF test files included
- [x] .env.example included
- [ ] LinkedIn video posted ← add link above after recording

---

<div align="center">

**Built for RIFT 2026 · HealthTech Track**

*"May your algorithms save lives."*

⚠️ Research and educational use only · Not for clinical decisions without physician review

</div>
