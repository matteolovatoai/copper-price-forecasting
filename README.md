# 📈 Copper Price Directional Forecasting (Machine Learning)

Questo progetto utilizza il Machine Learning per prevedere la **direzione giornaliera** (Su/Giù) del prezzo del Rame, analizzando le interdipendenze con il mercato delle valute e dell'energia.

## 🎯 Obiettivo del Progetto
Dimostrare come l'uso di modelli di classificazione possa supportare le decisioni di approvvigionamento aziendale (procurement). Invece di prevedere il prezzo esatto, il modello fornisce una probabilità statistica sul movimento del mercato il giorno successivo per ottimizzare il timing degli acquisti.

## 🛠️ Metodologia e Feature Engineering
Il modello è stato addestrato utilizzando i dati degli ultimi **2 anni** per catturare le dinamiche di mercato post-pandemiche.
- **Data Source:** Yahoo Finance (`yfinance`).
- **Input Features:** Rendimenti logaritmici e Trend (Medie Mobili) del **Dollaro Americano (DXY)** e del **Petrolio (Crude Oil)**.
- **Time Lags:** Sono stati integrati ritardi temporali (Lag) da 1 a 5 giorni per catturare la "memoria" del mercato.
- **Algoritmo:** `RandomForestClassifier` (Scikit-Learn).

## 📊 Analisi dei Risultati
Il modello finale ha raggiunto performance solide su dati reali (Test Set):
- **Accuracy Totale:** ~60%
- **Precision (Segnali di Acquisto):** ~65% 
  *(Quando il modello prevede un rialzo, la previsione è corretta quasi 2 volte su 3).*



## 🧠 Scoperte Chiave (Feature Importance)
L'analisi delle variabili ha rivelato che il prezzo del Rame non reagisce solo istantaneamente, ma segue segnali strutturati:
1. **Dominio dei Trend:** La variabile più importante è il **Trend del Petrolio (lag 2)**, indicando che il modello segue la direzione macro e non solo gli sbalzi giornalieri.
2. **Effetto Trasmissione:** Il **Dollaro (lag 4)** è tra le prime 4 variabili per importanza. Questo conferma un "effetto memoria": le variazioni valutarie impiegano circa 4 giorni lavorativi per riflettersi pienamente sul prezzo del metallo fisico.

---
*Progetto realizzato come caso studio di Data Science applicata alle Commodity e al Risk Management.*