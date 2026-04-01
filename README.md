# Retail Customer Fidelity Analysis (RFM)

## Obiettivo del progetto

Analizzare il comportamento dei clienti nel settore retail utilizzando un approccio RFM (Recency, Frequency, Monetary), con l’obiettivo di identificare segmenti ad alto valore e supportare decisioni di marketing, retention e crescita.

---

## Data Preparation & Exploratory Data Analysis (EDA)

Il dataset è stato costruito replicando la struttura di dati retail reali, mantenendo logiche di business coerenti e sostituendo le informazioni sensibili.

L’obiettivo di questa fase è stato preparare un dataset affidabile per analisi fidelity cliente e data visualization.

---

### Data Cleaning

#### 1. Validazione iniziale

* Verificata la completezza delle colonne chiave:

  * `ID_Card`
  * `Prezzo`
  * `Prodotto`
  * `Data`
* Nessun valore nullo rilevato nelle variabili critiche

#### 2. Coerenza dati (Business Logic)

Controlli effettuati per garantire coerenza con logiche retail reali:

* **Sesso ↔ Reparto**

  * Cliente M → Reparto Uomo
  * Cliente F → Reparto Donna

* **Prodotto ↔ Mondo**

  * T-shirt / Jeans → Casual
  * Scarpe / Felpe → Sport
  * Giacche → Luxury

* **Prezzo ↔ Categoria prodotto**

  * T-shirt: fascia bassa
  * Jeans / Felpe: fascia media
  * Giacche: fascia alta

#### 3. Gestione duplicati

* Verifica duplicati su chiavi transazionali:
  (`ID_Card`, `Data`, `Codice_Articolo`, `Prezzo`)
* Rimozione dei duplicati per evitare distorsioni nelle metriche cliente

#### 4. Controllo outlier

* Analisi della distribuzione dei prezzi
* Verifica coerenza rispetto alla categoria prodotto

---

### Data Transformation

#### Creazione variabili temporali

* Creazione della colonna `Data` a partire da `Anno`, `Mese`, `Giorno`
* Aggiunta di:

  * `Giorno_Settimana`
  * `Weekend` (flag booleano)

#### Standardizzazione

* Uniformati valori categorici
* Conversione corretta dei tipi dati (date, numeri, categorie)

---

### Exploratory Data Analysis (EDA)

L’analisi esplorativa è stata utilizzata per validare la qualità dei dati e identificare pattern rilevanti.

#### Analisi temporale

* Vendite per giorno della settimana
* Confronto weekend vs weekday
* Identificazione picchi di vendita

#### Analisi prodotti

* Vendite per prodotto e categoria (Mondo)
* Coerenza tra volume e fascia prezzo

#### Analisi clienti

* Frequenza acquisti per cliente
* Distribuzione spesa
* Identificazione clienti ricorrenti vs occasionali

#### Analisi prezzo

* Distribuzione prezzi per categoria
* Verifica clustering naturale delle fasce

---

## Customer Analysis & RFM Modeling

Sono state costruite metriche di fidelity cliente:

* **Monetary** → Spesa totale per cliente
* **Frequency** → Numero acquisti per cliente
* **Recency** → Giorni dall’ultimo acquisto

### Segmentazione clienti

* **Top Client** → alta spesa e alta frequenza
* **Medium Client** → valore intermedio
* **Low Client** → bassa spesa

### Stato cliente (Recency)

* **Attivo (≤ 30 giorni)**
* **A rischio (31–90 giorni)**
* **Perso (> 90 giorni)**

---

## Dashboard (Power BI)

La dashboard è strutturata in tre sezioni principali:

### Overview Vendite

* KPI: Totale vendite, Numero clienti, Spesa media
* Trend temporale
* Performance per negozio e prodotto

### Analisi Clienti

* Segmentazione clienti
* Distribuzione spesa (long-tail)
* Distribuzione frequenza acquisti
* Top clienti

### Fidelity & Retention

* Distribuzione Recency
* Clienti attivi vs a rischio vs persi
* Analisi frequenza e spesa per stato cliente

---
## 📥 Download Dashboard

[https://drive.google.com/file/d/1yR4VPDIUWYwXLiLVmUzszkCvtUlbShK1/view?usp=sharing]


<img width="700" height="400" alt="Screenshot 2026-04-01 162631" src="https://github.com/user-attachments/assets/67eff33a-d741-405c-bc5b-fd19da298f66" />

---

## Key Insights

### 1. Concentrazione del fatturato

Il fatturato è concentrato su una minoranza di clienti ad alto valore, mentre la maggior parte genera una spesa contenuta.

**Business action:**

* Fidelizzazione Top Client
* Strategie di retention

---

### 2. Distribuzione clienti

La maggioranza dei clienti appartiene al segmento Medium, indicando opportunità di crescita.

**Business action:**

* Upselling verso Top Client

---

### 3. Distribuzione della spesa

La distribuzione evidenzia una coda lunga con pochi high spender che generano gran parte del valore.

**Business action:**

* Personalizzazione offerte
* Segmentazione marketing

---

### 4. Frequenza e retention

I clienti attivi mostrano una frequenza maggiore rispetto ai clienti persi.

**Business action:**

* Aumentare frequenza → migliorare retention

---

### 5. Recency e churn

Una quota significativa di clienti risulta inattiva.

**Business action:**

* Campagne di re-engagement
* Offerte mirate

---

### 6. Perdita di valore

Una parte del fatturato deriva da clienti oggi inattivi.

**Business action:**

* Strategie di recupero clienti

---

### 7. Differenze tra negozi

I negozi principali generano la maggior parte del fatturato.

**Business action:**

* Replicare strategie dei top store
* Ottimizzare quelli meno performanti

---

### 8. Mix prodotto

I prodotti ad alto volume non coincidono sempre con quelli a maggiore valore.

**Business action:**

* Ottimizzazione assortimento
* Cross-selling

---

## Conclusioni

Il progetto dimostra come l’integrazione di analisi dati e logiche di business permetta di:

* Identificare segmenti ad alto valore
* Migliorare la retention clienti
* Supportare decisioni strategiche

---

## Tech Stack

* Python (Pandas, NumPy)
* Power BI
* Data Cleaning & Feature Engineering
* Customer Analytics (RFM)
