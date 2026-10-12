# 🏠 Gestore delle spese domestiche



> Un'applicazione CLI interattiva sviluppata in Python per tracciare le spese domestiche, gestire la persistenza dei dati su file CSV, generare report mensili ordinati e identificare le transazioni più rilevanti.

---

## 📌 Panoramica del progetto
Questo progetto dimostra competenze solide nei fondamenti di programmazione in Python, nella gestione dei file I/O e nella scrittura di codice pulito e modulare. L'applicazione non richiede database esterni o librerie di terze parti, sfruttando interamente la libreria standard per offrire un sistema leggero, robusto e facilmente eseguibile.

---

## ✨ Funzionalità e architettura del codice
Il programma è suddiviso in funzioni logiche e specializzate:

* **Persistenza dei dati (`check_if_file_exists`):** verifica automaticamente l'esistenza del file di storico (`transaction_history.csv`) e lo inizializza con le intestazioni di colonna (`data`, `descrizione`, `importo`) se non è presente
* **Controllo dello stato (`file_is_empty`):** Esegue controlli preventivi sul dataset per evitare errori durante l'analisi delle transazioni
* **Inserimento guidato e validazione (`add_transaction`):** Permette all'utente di registrare una nuova spesa inserendo data (`GG/MM/AAAA`), importo e descrizione, con blocchi di gestione delle eccezioni (`try-except`) per prevenire crash dovuti a input non validi
* **Reportistica cronologica (`show_report`):** Legge i dati dal CSV, converte e formatta le date tramite il modulo `datetime`, ordinando le transazioni cronologicamente per anno e mese con un'impaginazione dinamica basata sulla lunghezza delle descrizioni
* **Analisi top 10 (`show_top_transactions`):** Estrae e ordina le spese in modalità decrescente tramite funzioni `lambda` per evidenziare le 10 voci con l'importo più elevato
* **Interfaccia interattiva:** Un menu testuale basato su un ciclo `while` continuo gestisce le scelte dell'utente con validazione rigorosa tramite `assert` ed eccezioni.

---

## 🛠️ Tecnologie e librerie utilizzate
Il progetto è scritto interamente in **Python** e utilizza esclusivamente la libreria standard:
* `csv`: per la lettura e la scrittura dei file di storico transazioni
* `os`: per la verifica e la gestione dei percorsi dei file nel file system
* `datetime`: per il parsing, la formattazione e l'ordinamento basato sulla cronologia temporale.

---

## 🚀 Come eseguire il progetto

È possibile testare il codice in pochi secondi tramite Google Colab oppure eseguirlo in locale tramite strumenti come Jupyter Notebook.
Per testare il programma con una quantità di dati opportuni si può utilizzare il file transaction_history.csv.
