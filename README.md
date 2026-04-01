## Data Preparation & Exploratory Data Analysis (EDA)

Il dataset è stato costruito replicando la struttura di dati retail reali, mantenendo logiche di business coerenti e sostituendo le informazioni sensibili.

L’obiettivo di questa fase è stato preparare un dataset affidabile per analisi del comportamento cliente (fidelity) e data visualization.

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

Sono stati effettuati controlli per garantire coerenza rispetto a logiche retail reali:

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
* Rimozione dei record duplicati per evitare distorsioni nelle metriche cliente

#### 4. Controllo outlier

* Analisi distribuzione prezzi per categoria
* Verifica assenza di valori fuori scala rispetto al prodotto

---

### Data Transformation

#### Creazione variabili temporali

* Generata colonna `Data` a partire da:

  * `Anno`, `Mese`, `Giorno`
* Aggiunte:

  * `Giorno_Settimana`
  * `Weekend` (flag booleano)

#### Standardizzazione

* Uniformati valori categorici (es. naming consistente)
* Conversione tipi dati (date, numerici, categorici)

---

### Exploratory Data Analysis (EDA)

L’analisi esplorativa è stata condotta per verificare la qualità del dataset e identificare pattern utili per la fase successiva.

#### Analisi temporale

* Distribuzione delle vendite per:

  * Giorno della settimana
  * Weekend vs weekday
* Identificazione di picchi di vendita nei weekend

#### Analisi prodotti

* Distribuzione vendite per:

  * Prodotto
  * Mondo (Casual, Sport, Luxury)
* Verifica coerenza tra volumi e fascia prezzo

#### Analisi clienti

* Frequenza acquisti per `ID_Card`
* Distribuzione spesa per cliente
* Identificazione di clienti ricorrenti vs occasionali

#### Analisi prezzo

* Distribuzione prezzi per categoria prodotto
* Verifica clustering naturale delle fasce di prezzo

---

### Output

Il dataset risultante è:

* Pulito e consistente
* Allineato a logiche di business retail
* Arricchito con variabili temporali
* Pronto per:

  * Data visualization (Power BI)
  * Analisi fidelity cliente
  * Segmentazione comportamentale

---

### Next Step

La fase successiva prevede:

* Costruzione metriche fidelity (RFM)
* Segmentazione clienti
* Sviluppo dashboard interattiva in Power BI
