<div align="center">

# 🧬 PharmaGuard

</div>

---

# He Was 2 Years Old.

He was a healthy little boy. 13 kilograms. Bright eyes. A routine surgery to help him breathe better at night — an adenotonsillectomy for sleep apnea.

His parents brought him home the next day. The doctors sent him with a prescription for codeine. Standard dose. Age-appropriate. By the book.

He never woke up again.

His autopsy revealed morphine levels of **32 nanograms per milliliter** in his blood — far beyond toxic levels. The dose he received was not wrong. It was exactly what any doctor would prescribe.

But his body carried a genetic mutation — **CYP2D6 ultrarapid metabolizer** — that converted codeine into pure morphine at 3 to 4 times the normal rate. His small body was flooded with opioids. His breathing stopped in his sleep.

This case was published in the **New England Journal of Medicine in 2009**.

*His doctors didn't know. His parents didn't know. Nobody checked his DNA.*

---

# He Was Not Alone.

In 2012, **three more children** died or nearly died the same way. Same surgery. Same drug. Same preventable genetic mismatch. Published in *Pediatrics* journal. Reported to the FDA.

The FDA reviewed their records — **64 documented cases** of serious harm from codeine between 2000 and 2013. **24 of those cases were fatal. 21 of the deaths were children under 12.**

In nearly every case where genetic testing was done after the fact, the child was a CYP2D6 ultrarapid metabolizer.

A 15-month-old. A 2-year-old. A 3-year-old. A 4-year-old.

All given the correct dose. All given the correct drug. All dead because nobody checked a gene that a simple test could have identified.

> *In 2013, the FDA added its strongest possible warning — a Black Box — to every codeine product in America.*
> *The European Medicines Agency banned codeine in children under 12 in 2015.*
>
> *And yet, in countries around the world, codeine is still prescribed without genetic testing.*

---

# The Numbers Are Staggering.

Prescription drugs in the U.S. cause an estimated **2.74 million adverse drug reactions** and **128,000 deaths annually**.

**98% of people** in the U.S. carry at least one high-risk genomic variant in one of the 12 most-tested pharmacogenetic genes.

That means almost everyone reading this README right now carries a variant that affects how they process at least one drug. They just don't know which one.

About **3% of African-Americans, 1–10% of white populations, and 11–30% of North Africans** are CYP2D6 ultrarapid metabolizers. Millions of people. Billions of prescriptions written every year. Zero genetic checks at the point of prescribing.

The science to prevent this has existed for **decades.**

The barrier was never the biology. It was the tool.

---

# We Built the Tool.

<div align="center">

## PharmaGuard
### *AI-Powered Drug Safety from Your DNA*

**RIFT 2026 Hackathon · HealthTech Track · Problem Statement 2 — Precision Medicine**

### 🌐 [Live Application → pharmaguard.onrender.com](https://pharmaguard.onrender.com)
### 🎥 [Demo Video → LinkedIn](https://linkedin.com/YOUR_VIDEO_LINK)
`#RIFT2026` `#PharmaGuard` `#Pharmacogenomics` `#AIinHealthcare`

</div>

Upload a patient's genetic file. Select a drug. Get the truth in seconds.

```
Patient VCF file  +  Drug Name
         ↓
   SAFE ✅  or  ADJUST DOSE ⚠️  or  TOXIC ☠️  or  INEFFECTIVE ❌
         ↓
   Full clinical explanation. Variant citations. CPIC guidelines. Alternative drugs.
```

Not a guess. Not a population average. A **personalized prediction for this patient, right now.**

---

# Try It In 30 Seconds

```
1. Open → pharmaguard.onrender.com
2. Click "Load Sample Patient VCF"
3. Click CODEINE
4. Click "Analyze with AI"
```

Watch the system flag: **🔴 TOXIC — CRITICAL RISK. CYP2D6 *4/*4 detected.**

Then imagine that patient is the 2-year-old boy from the New England Journal of Medicine.

Imagine his parents in the waiting room.

Imagine PharmaGuard was open on the doctor's screen when they wrote that prescription.

---

# The 6 Genes. The 6 Drugs. The Real Human Cost.

These are not hypothetical risks. These are documented deaths, published in peer-reviewed journals, reviewed by the FDA.

| Gene | Drug | What Happens Without Testing | Real Cases |
|------|------|------------------------------|------------|
| **CYP2D6** | Codeine | Ultrarapid metabolizers convert it to fatal morphine doses | 24 deaths documented by FDA (2000–2013) |
| **CYP2C19** | Clopidogrel | Poor metabolizers can't activate it — heart attack prevention fails silently | Millions prescribed annually without testing |
| **CYP2C9** | Warfarin | Wrong dose causes uncontrollable internal bleeding | Leading cause of drug-related ER visits in the US |
| **SLCO1B1** | Simvastatin | Statins accumulate — muscles dissolve into the bloodstream | Rhabdomyolysis: documented, devastating, preventable |
| **TPMT** | Azathioprine | Immune suppression destroys bone marrow | Variant present in ~10% of population |
| **DPYD** | Fluorouracil | Chemotherapy builds to lethal concentrations | DPD deficiency affects ~8% of Europeans |

In one landmark study of codeine-related deaths in Ontario, Canada, approximately **51% of the deaths involved the use of a CYP2D6 inhibitor — commonly an antidepressant — concurrently with codeine.**

They were taking their antidepressant. And their pain medication. Two drugs their doctors each prescribed correctly. Together, they were fatal. A genetic test would have flagged the interaction.

---

# How PharmaGuard Works

```
┌──────────────────────────────────────────────┐
│               THE CLINICIAN                  │
│  Uploads VCF · Selects drug · Sees the truth │
└─────────────────────┬────────────────────────┘
                      │
┌─────────────────────▼────────────────────────┐
│            PHARMAGUARD BACKEND               │
│                                              │
│  Reads the COMPLETE raw VCF file             │
│  Builds precise pharmacogenomics prompt      │
│  Sends to Gemini AI — most capable model     │
│  Auto-retries on rate limits                 │
│  Returns schema-compliant clinical JSON      │
└──────────┬─────────────────┬─────────────────┘
           ▼                 ▼
     Google Gemini         Groq AI
      2.0 Flash         Llama 3.3 70B
      (Primary)          (Fallback)
```

We send the **entire raw VCF** to the AI — not summaries, not shortcuts. Because when a child's life is on the line, approximation is not acceptable.

---

# Tech Stack

| Layer | Technology |
|-------|-----------|
| 🖥️ Frontend | HTML · CSS · Vanilla JS |
| ⚙️ Backend | Node.js · Express |
| 🧠 Primary AI | Google Gemini 2.0 Flash |
| 🔄 Fallback | Groq — Llama 3.3 70B (14,400 free req/day) |
| 🌐 Fallback | OpenRouter — DeepSeek · Mistral |
| 🚀 Hosting | Render.com |
| 📋 Standards | **CPIC Level A Guidelines** — Clinical gold standard |

---

# The Output That Matters

Every analysis produces structured, schema-compliant JSON — ready for EHR integration, clinical audit, or regulatory review:

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
      {
        "rsid": "rs3892097",
        "chrom": "chr22",
        "pos": "42526694",
        "ref": "G",
        "alt": "A",
        "gene": "CYP2D6",
        "star_allele": "*4",
        "impact": "HIGH"
      }
    ]
  },
  "clinical_recommendation": {
    "summary": "CONTRAINDICATED. This patient cannot safely metabolize codeine. Do not prescribe. Use morphine or a non-CYP2D6 opioid alternative.",
    "cpic_guideline": "https://cpicpgx.org/guidelines/codeine/",
    "alternative_drugs": ["morphine", "oxymorphone", "buprenorphine", "fentanyl"],
    "monitoring_required": true
  },
  "llm_generated_explanation": {
    "summary": "Patient carries CYP2D6 *4/*4 diplotype (rs3892097 G>A). This produces zero active CYP2D6 enzyme. Codeine accumulates without conversion, causing paradoxical toxicity at standard doses.",
    "biological_mechanism": "The *4 allele introduces a splice site mutation at position 1846 that disrupts CYP2D6 mRNA processing, producing a non-functional truncated protein.",
    "clinical_context": "CPIC Level A directive: codeine is contraindicated in CYP2D6 ultrarapid metabolizers. This is not a recommendation — it is a clinical directive backed by documented fatalities.",
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

# Test Files for Judges

Three real-world genetic profiles for immediate testing:

| File | The Patient Profile | What You'll See |
|------|--------------------|----|
| `patient_high_risk.vcf` | CYP2D6\*4/\*4 · TPMT\*3A · DPYD\*2A | 🔴 Toxic / Contraindicated |
| `patient_normal.vcf` | All \*1/\*1 reference alleles | 🟢 Safe / Standard dosing |
| `patient_intermediate.vcf` | Mixed CYP2D6\*4/\*1 · SLCO1B1\*5 | 🟡 Adjust Dosage |

---

# Run It Yourself

```bash
git clone https://github.com/ankurojha834/pharmaguard.git
cd pharmaguard
npm install

# Create .env file with:
GEMINI_API_KEY=your_key    # aistudio.google.com/app/apikey (free)
GROQ_API_KEY=your_key      # console.groq.com (free, generous)

npm start
# Open http://localhost:3001
```

---

# API

| Endpoint | Method | What It Does |
|----------|--------|-------------|
| `/api/ai` | POST | Send VCF + drug → AI analysis |
| `/health` | GET | Server status + API key check |

---

# Project Structure

```
pharmaguard/
├── public/index.html          ← Complete frontend UI
├── samples/
│   ├── patient_high_risk.vcf
│   ├── patient_normal.vcf
│   └── patient_intermediate.vcf
├── server.js                  ← Secure backend + multi-AI proxy
├── package.json
├── render.yaml                ← One-click Render deployment
└── .env.example
```

---

# The Team

| Name | Role |
|------|------|
| **Ankur Ojha** | Full Stack + AI Integration |
| **[Team Member]** | [Role] |

---

# Submission Checklist

- [x] Live deployed application
- [x] Public GitHub repository
- [x] VCF file upload with drag-and-drop
- [x] JSON output — exact schema match, field by field
- [x] All 6 pharmacogenes: CYP2D6, CYP2C19, CYP2C9, SLCO1B1, TPMT, DPYD
- [x] All 6 drugs + custom drug input
- [x] LLM explanations with specific variant citations
- [x] CPIC Level A aligned recommendations
- [x] 3 sample VCF test files
- [x] .env.example included
- [x] Multi-AI with auto-retry (Gemini + Groq + OpenRouter)
- [ ] LinkedIn video — add link before submitting

---

<div align="center">

---

## The 2-year-old from the *New England Journal of Medicine* didn't have a name in the published case report.

## He was listed as "a previously healthy toddler."

## His parents are still alive. His doctors are still practicing.

## Nobody was at fault. Nobody checked his DNA.

---

### **We built PharmaGuard so that the next child has a chance.**

---

*Sources: New England Journal of Medicine (2009, 2013) · Pediatrics (2012) · FDA Adverse Event Reports · NCBI/PubMed · CPIC Guidelines*

*RIFT 2026 · HealthTech Track · Built in 24 hours with purpose*

⚠️ For research and educational purposes only · Clinical decisions require physician oversight

</div>
