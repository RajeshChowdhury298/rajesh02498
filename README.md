# HPCL Sentinel: AI-Driven B2B Sales Intelligence

## 🚀 Overview
**HPCL Sentinel** is an end-to-end sales intelligence platform designed to bridge the discovery gap in HPCL Direct Sales (DS). By autonomously harvesting public signals, the system identifies high-intent B2B leads, maps them to the HPCL product portfolio, and delivers actionable sales dossiers directly to officers via WhatsApp.

---

## ✨ Core Features
- **Signal Discovery Engine**: Monitors web news, government tenders, and corporate filings to detect "operational cues" (e.g., road construction, plant expansions).
- **Product-Need Inference**: Uses Natural Language Processing (NLP) to anchor signals to specific HPCL products like Bitumen, HSD, FO, and Specialty Oils.
- **Strategic Lead Dossiers**: Provides officers with entity resolution, logistical proximity to the nearest HPCL terminal, and a pre-written "Sales Script".
- **Mobile-First Delivery**: Real-time WhatsApp alerts via API integration for immediate field action.
- **Executive Strategy Dashboard**: High-level visualization of conversion funnels, geographic demand heatmaps, and weekly discovery velocity.
- **Closed-Loop Feedback**: A dedicated interface for Sales Officers to "Accept," "Reject," or "Convert" leads, which retrains the AI model to reduce false positives.

---

## 🛠 Technology Stack
- **Frontend**: Next.js, Tailwind CSS, Recharts (Executive Dashboard)
- **Backend**: Python (FastAPI), Supabase (PostgreSQL)
- **AI/ML**: NLP-based keyword extraction and intent scoring
- **Integration**: WhatsApp Business API (via Twilio/Sandbox)

---

## 📊 Meeting PS Requirements

| Requirement | Implementation Detail |
| :--- | :--- |
| **1. Source Governance** | Tracks 600+ validated leads with full source traceability. |
| **2. Inference Engine** | Automatically maps "expressway" signals to Bitumen portfolio. |
| **3. Geography Heatmap** | Visualizes state-wise demand intensity (WB, TN, GJ, etc.). |
| **4. Feedback Loop** | Captures "Wrong Product" or "Rejection" codes to refine AI scoring. |

---

## 🏗 Deployment Architecture
The architecture is designed to meet HPCL’s Non-Functional Requirements for **Auditability, Scalability, and Security**. It follows a Decoupled Event-Driven Microservices pattern.

### 1. High-Level Data Flow
1. **Ingestion (The Harvester)**: Autonomous Python scrapers monitor News, Tenders, and Filings.
2. **Processing (The Brain)**: Raw text passes through the Inference Engine for Entity Resolution and Intent Scoring.
3. **Persistence**: Structured leads are stored in **Supabase (PostgreSQL)** with a `trust_score`.
4. **Action**: WhatsApp Gateway triggers encrypted alerts to Sales Officers.

### 2. Component Breakdown
- **Web Intelligence Layer**: Next.js (App Router) with RBAC for Executive vs. Field views.
- **Intelligence Layer**: FastAPI / Python for async processing and Semantic Keyword Mapping.
- **Feedback Loop API**: Handles "Weight Recalibration" based on field rejections/conversions.
- **Infrastructure**: Supabase for real-time listeners and Twilio for enterprise-grade alerts.

---

## 🛡 Security & Compliance
- **Data Privacy**: Focuses on corporate signals and avoids PII, complying with enterprise policies.
- **Encryption**: All communication is secured via HTTPS/TLS.
- **Auditability**: Every lead is "anchored" to its original source URL for full legitimacy verification.

---

## ⚙️ Setup Instructions
1. **Clone the repository**: `git clone https://github.com/RajeshChowdhury298/rajesh02498.git`
2. **Install dependencies**: `npm install`
3. **Environment Setup**: Create a `.env.local` file with your `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_ANON_KEY`.
4. **Run Development Server**: `npm run dev`
