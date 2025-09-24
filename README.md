# ALM-IRRBB
## Obiettivo
Costruire un mini-motore IRRBB (Interest Rate Risk in the Banking Book) che, dato una curva dei tassi e un portafoglio, calcola:

a. *ΔNII* (12 mesi): variazione del margine di interesse annuale quando i tassi si muovono.

b. *ΔEVE*: variazione del valore economico (ad oggi) del portafoglio sotto scenari di curva.

Include controlli di qualità dati e una dashboard per visualizzare risultati e grafici (repricing gaps, KRD, waterfall ΔEVE).

## Glossario
- IRRBB (Interest Rate Risk in the Banking Book): rischio che i tassi d’interesse cambino e facciano variare:
  - i ricavi da interessi che la banca incassa nell’anno (~12 mesi),
  - il valore economico dei suoi attivi/passivi (prestiti, depositi, bond) “non di trading”.
- NII (Net Interest Income): margine di interesse dell’anno: interessi incassati – interessi pagati.
- EVE (Economic Value of Equity): variazione del valore attuale del portafoglio quando i tassi si muovono (quanto “vale” in più o in meno oggi).

- Repricing gap: differenza tra quanto delle tue posizioni riprezza “presto” e “tardi” (es. prestiti a tasso variabile vs depositi fermi).

- Shock di curva: uno scenario sui tassi (es. tutti i tassi +2%, o solo i tassi corti su, o curva più ripida/piatta).

- KRD (Key-Rate Durations): sensibilità del valore in punti specifici della curva (es. 6M, 1Y, 2Y, 5Y, 10Y).

- PV / DF (Present Value / Discount Factor): valore attuale e fattore di sconto per portare un flusso futuro a “oggi”.

- NMD (Non-Maturity Deposits): depositi senza scadenza (conti a vista). Si modellano come se avessero una “scadenza finta” (portafoglio replicante).

- Lag/Beta sui NMD: i tassi dei depositi non seguono subito (lag) e non seguono del tutto (beta < 1) i movimenti dei tassi di mercato.

- Basis risk: attivi/passivi indicizzati a indici diversi (es. ESTR vs Euribor) → si muovono in modo diverso.

- Steepener/Flattener: curva più ripida (lunghi su, corti giù) / più piatta (lunghi giù, corti su).

## Strumenti (free)

- Python: linguaggio principale.

- pandas/numpy: tabelle e calcoli.

- DuckDB + Parquet: salvare/leggere dati velocemente in locale.

- Great Expectations: controlli di qualità dati (es. “i tassi sono nel range giusto?”).

- Prefect: fa partire l’intera pipeline in un click (ingest → calcoli → report).

- Streamlit: dashboard per vedere gap, grafici e risultati.

