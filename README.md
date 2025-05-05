# Student Habits & Performance ML Pipeline

## Descrizione

Questo repository contiene uno script Python per l'analisi e la predizione dei punteggi d'esame (`exam_score`) di studenti, basato sulle abitudini di studio, stile di vita e partecipazione ad attività extra-scolastiche. Il flusso di lavoro comprende:

1. **Caricamento e pulizia dati** (rimozione ID, imputazione valori mancanti)
2. **Encoding variabili categoriali** (OrdinalEncoder e LabelEncoder)
3. **Feature engineering** (es. `entertainment_time`)
4. **Selezione delle feature** tramite VIF e p-value per ridurre multicollinearità
5. **Training dei modelli**:

   * Regressione Lineare
   * XGBoost (base e ottimizzato via GridSearchCV)
6. **Valutazione e confronto** dei modelli (R², RMSE)
7. **Visualizzazioni**:

   * Distribuzione dei punteggi
   * Matrici di correlazione
   * Grafico "Reali vs Predetti" per ciascun modello (in un unico pannello)
   * Boxplot dei residui per individuare outlier
   * Confronto Reali vs Predetti prima/dopo rimozione outlier (Linear)
8. **Outlier detection e rimozione** (IQR sui residui) e ricalcolo delle metriche

## Struttura del repository

```
├── student.csv   # Dataset grezzo
├── examScore.py                   # Script Python completo
├── README.md                        # Questo file
└── requirements.txt                 # Dipendenze Python
```

## Requisiti

* Python 3.8+
* pacchetti Python (vedi `requirements.txt`)

### Dipendenze principali

```bash
numpy
pandas
matplotlib
seaborn
statsmodels
scikit-learn
xgboost
```

## Installazione

1. Clona il repository:

   ```bash
   ```

git clone [https://github.com/JacobHess03/ML-Analysis-StudentHabitsPerformance](https://github.com/JacobHess03/ML-Analysis-StudentHabitsPerformance)
cd ML-Analysis-StudentHabitsPerformance

````
2. Crea un ambiente virtuale e attivalo:
   ```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\\Scripts\\activate     # Windows
````

3. Installa le dipendenze:

   ```bash
   ```

pip install -r requirements.txt

````

## Utilizzo
Esegui lo script direttamente:
```bash
python examScore.py
````

Lo script stamperà metriche di performance e mostrerà tutti i grafici in sequenza.

### Personalizzazioni

* **File di input**: Modifica il percorso `file_path` in `examScore.py` per puntare al tuo dataset.
* **Parametri di GridSearch**: Nel dizionario `param_grid` puoi aggiungere o rimuovere parametri per XGBoost.
* **Soglia VIF/p-value**: Adatta i valori di `vif_threshold` e `pvalue_threshold` nella funzione `elimina_variabili_vif_pvalue`.

## Risultati attesi

* Plot di distribuzione dei punteggi d'esame
* Heatmap di correlazione
* Tabella comparativa delle metriche R² e RMSE
* Grafici Reali vs Predetti per ogni modello
* Boxplot dei residui e scatter confronti prima/dopo rimozione outlier

## Contributi

Pull request e segnalazioni di issue sono benvenuti!

## Licenza

Questo progetto è rilasciato sotto licenza MIT.

---

*Autore: Giacomo Visciotti-Simone Verrengia-Giuseppe Del Vecchio*



