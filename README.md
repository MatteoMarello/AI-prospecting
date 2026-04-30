# LeadSignal AI - Prospect Intelligence Engine

**Versione:** 1.0 (Pre-MVP - Setup Fase 1)  
**Stato:** Repository Setup + Planning  
**Ultimo aggiornamento:** 2026-04-30

---

## 📋 Descrizione Progetto

LeadSignal AI trasforma siti web e segnali digitali in opportunità commerciali pronte da contattare per agenzie marketing, web agency, consulenti B2B e software house.

**Value Proposition:** Invece di consegnare liste di contatti generiche, il sistema:
- Trova aziende target in una nicchia specifica
- Analizza automaticamente il loro sito e presenza digitale
- Produce mini-audit personalizzati con problemi visibili
- Genera messaggi di contatto pronti per email e LinkedIn
- Assegna uno score di priorità commerciale

**Obiettivo economico:** 2.000 euro/mese ricorrenti (es: 4 clienti @499€/mese)

---

## 🎯 Cliente Ideale

### Target Primario
- Web agency piccole/medie
- Agenzie marketing locali
- Consulenti SEO
- Consulenti advertising
- Software house (vendita siti, CRM, gestionali)
- Consulenti B2B ad alto ticket

### Nicchia Iniziale (Pilot)
Web agency che vendono siti, SEO, advertising a:
- Dentisti
- Cliniche estetiche
- Studi medici privati
- Palestre premium
- Agenzie immobiliari
- Hotel e strutture ricettive
- Studi legali
- Consulenti finanziari
- Ristoranti premium

---

## 📦 Offerta Commerciale (Roadmap Pricing)

### Pilot Pack (Validazione)
**Prezzo:** 149€ (one-time)
- 20 aziende target
- 10 mini-audit sintetici
- 5 audit completi
- Scores di priorità
- Messaggi email personalizzati
- Delivery in Google Sheet
- Call conclusiva 30 minuti

### Abbonamento Base
**Prezzo:** 299€/mese
- 50 prospect/mese
- 20 mini-audit
- 10 messaggi personalizzati
- Database aggiornato
- Report mensile

### Abbonamento Pro
**Prezzo:** 499€/mese
- 100 prospect/mese
- 50 mini-audit
- 20 audit completi
- Email + LinkedIn messages
- Segmentazione per priorità
- Export CSV/Sheet/CRM

### Abbonamento Premium
**Prezzo:** 799-999€/mese
- 200 prospect/mese
- Audit completi best prospects
- Sequenze email complete
- Setup CRM/Instantly/Lemlist
- Monitoraggio risposte
- Dashboard performance

---

## 🏗️ Architettura - Moduli Principali

```
Ricerca Prospect
       ↓
Raccolta Dati Pubblici
       ↓
Analisi Sito (Tecnica + AI)
       ↓
Generazione Mini-Audit
       ↓
Scoring Commerciale
       ↓
Generazione Messaggi
       ↓
Dashboard Cliente / Export
```

### Modulo 1: Ricerca Prospect
- Input: nicchia, area geografica, servizio da vendere
- Output: lista aziende + sito + categoria + località

### Modulo 2: Raccolta Dati Pubblici
- Siti web aziendali
- Directory pubbliche
- Google Maps (con limiti)
- Social public data
- Job posting
- News locali

### Modulo 3: Analisi Sito
**Analisi Deterministiche:**
- Page speed (mobile/desktop)
- Mobile responsiveness
- SSL
- Meta tags (title, description)
- H1/H2 structure
- Form presenti
- Link rotti
- Tech stack (BuiltWith)

**Analisi AI:**
- Chiarezza messaggio
- Qualità posizionamento
- Problemi conversione
- Trust signals
- Angolo commerciale
- Sintesi problemi

### Modulo 4: Tipi di Audit (Modulari)
- **Audit Conversione:** CTA, hero section, form, telefono, percorso prenotazione
- **Audit Trust:** Recensioni, testimonianze, case study, team, certificazioni
- **Audit Tecnico:** Velocità, mobile, errori, SSL, sitemap, meta
- **Audit SEO/Local:** Keywords, pagine, contenuti locali, GBP, competitor
- **Audit AI Visibility:** Entità azienda, NAP, schema markup, directory
- **Audit Offerta:** Differenziazione, promessa, benefici, pricing, proof

### Modulo 5: Scoring Prospect (1-5 scale)
Considera: fit, budget probabile, gravità problemi, urgenza, facilità contatto, ROI potenziale

### Modulo 6: Generazione Messaggi
- Email principal
- Follow-up 1, 2
- Messaggio LinkedIn
- Script chiamata
- Tono: specifico, non aggressivo, basato su evidenze

### Modulo 7: Dashboard Cliente
- Prospect generati + scores
- Audit + messaggi
- Export (CSV, Sheets, Airtable, HubSpot, Pipedrive)
- Tracking risposte (futuro)

---

## 📊 Database Schema (Prospect Record)

### Campi Anagrafici
- `id_prospect`
- `nome_azienda`
- `sito`
- `settore` / `sottosettore`
- `paese` / `regione` / `citta`
- `fonte`
- `data_raccolta`

### Campi Digitali (Deterministic)
- `has_ssl`
- `page_speed_mobile`
- `page_speed_desktop`
- `meta_title`
- `meta_description`
- `h1_present`
- `tech_stack`
- `has_contact_form`
- `has_phone`
- `has_whatsapp`
- `has_booking_system`
- `has_reviews`
- `has_case_studies`

### Campi AI (Analysis)
- `company_summary`
- `main_problem`
- `secondary_problems`
- `commercial_opportunity`
- `message_angle`
- `score_fit` (0-100)
- `score_pain` (0-100)
- `score_budget` (0-100)
- `priority_score` (1-5)
- `confidence_level`

### Campi Outreach
- `email_generated`
- `linkedin_message`
- `followup_1`
- `followup_2`
- `contact_status`
- `last_contact_date`
- `response`
- `client_notes`

---

## 🔄 Fasi di Sviluppo

### **Fase 1: MVP 0 - Validazione Manuale (2-3 settimane)**
Status: **ATTUALE**

✅ Strumenti:
- Google Sheets
- ChatGPT / Claude
- Browser + tools manuali
- PageSpeed Insights
- BuiltWith / Wappalyzer

📋 Deliverables:
- Template Google Sheet
- Template mini-audit
- Prompt standard
- 10-20 esempi reali
- Landing page semplice
- Script outreach

🎯 Obiettivo:
- Validare che clienti paghino pilot
- Misurare: quante agenzie rispondono positivamente

---

### **Fase 2: MVP 1 - Automazione Audit (3-6 settimane)**
Status: PLANNED

- Script Python per analisi tecnica
- API LLM (OpenAI/Claude) per AI analysis
- Google Sheets API per export
- Screenshot automatici
- Generazione PDF
- Riduzione tempo audit da 20-40 min → 2-5 min

---

### **Fase 3: MVP 2 - Campagne Multi-Cliente (1-2 mesi)**
Status: PLANNED

- Profilo cliente pagante
- Gestione campagne multi-prospect
- Report multipli + batch processing
- Dashboard base
- Generazione PDF automatica

---

### **Fase 4: SaaS Leggero (Dopo validazione commerciale)**
Status: FUTURE

- Web app con login
- Billing Stripe
- Database centralizzato
- Storico audit
- Export CRM multi-piattaforma
- Ruoli utente
- Monitoring costi API

---

## 📁 Struttura Repository

```
AI-prospecting/
├── README.md (questo file)
├── PROJECT_SPEC.md (spec completa originale)
├── ROADMAP.md (timeline dettagliata)
├── docs/
│   ├── 01_CLIENT_ONBOARDING.md (questionnaire cliente)
│   ├── 02_AUDIT_TEMPLATES.md (template audit per tipo)
│   ├── 03_PROMPT_LIBRARY.md (prompt standard AI)
│   ├── 04_SCORING_LOGIC.md (logica scoring)
│   └── 05_MESSAGING_TEMPLATES.md (template messaggi)
├── templates/
│   ├── google_sheet_template.md (setup sheet)
│   ├── audit_report_template.md (template audit)
│   ├── email_messages.md (esempi email)
│   └── linkedin_messages.md (esempi LinkedIn)
├── examples/
│   ├── example_01_dentist_clinic.md
│   ├── example_02_aesthetic_clinic.md
│   ├── example_03_gym_premium.md
│   └── example_04_law_firm.md
├── operations/
│   ├── day_01_03_planning.md
│   ├── day_04_07_demo_building.md
│   ├── day_08_15_outreach.md
│   ├── day_16_21_sales.md
│   └── day_22_30_delivery.md
├── metrics/
│   ├── internal_metrics.md (KPI produzione)
│   ├── commercial_metrics.md (KPI vendita)
│   └── client_metrics.md (KPI cliente)
├── compliance/
│   ├── GDPR_GUIDELINES.md
│   ├── DATA_SOURCES.md (fonti dati autorizzate)
│   └── LEGAL_CHECKLIST.md
└── .gitignore
```

---

## ✅ Checklist Setup Repository

- [x] README.md creato
- [ ] PROJECT_SPEC.md (copia spec)
- [ ] ROADMAP.md (timeline)
- [ ] Template docs/
- [ ] Esempi iniziali (examples/)
- [ ] Operazioni 30gg (operations/)
- [ ] Compliance docs
- [ ] .gitignore configurato

---

## 🚀 Prossimi Passi (Giorni 1-3)

1. **Scegliere nicchia pilot:**
   - Web agency → dentisti/cliniche estetiche/palestre

2. **Definire cliente ideale preciso:**
   - Questionnaire da compilare

3. **Preparare 3 esempi reali:**
   - Prospect
   - Mini-audit
   - Messaggio personalizzato

4. **Setup Google Sheet template:**
   - Colonne standard
   - Formule base
   - Filtri scoring

5. **Creare landing page semplicissima:**
   - Problema + soluzione
   - Esempio + CTA

6. **Scrivere script outreach:**
   - Messaggio LinkedIn/email
   - Offer pilot

---

## 📞 Contatti & Risorse

**Repository Owner:** @MatteoMarello  
**Progetto:** LeadSignal AI  
**Email (ipotetica):** [sera definire]  
**Status:** Pre-MVP Setup Phase

---

## 📜 Versione Document

| Data | Versione | Autore | Note |
|------|----------|--------|------|
| 2026-04-30 | 1.0 | MatteoMarello | Repository setup iniziale, nessun codice |

---

## 🔗 Link Utili

- [Project Specification (Completa)](./PROJECT_SPEC.md) - Spec dettagliata originale
- [30-Day Operational Plan](./operations/) - Piano giorno per giorno
- [Audit Templates](./docs/02_AUDIT_TEMPLATES.md) - Template per audit
- [Scoring Logic](./docs/04_SCORING_LOGIC.md) - Come calcolare priority score

---

**Nota:** Questo è il setup iniziale. Nessun codice è stato scritto. Il focus è su planning, templates, e validazione commerciale manuale prima di automazione.

