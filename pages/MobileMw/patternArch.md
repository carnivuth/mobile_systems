# PATTERN ARCHITETTURALI

Sono generali, non solo per Mobile:
- **a livelli**: architettura multistrato in cui le responsabilità sono assegnate ai vari livelli
- **client-server** (più usato): i client usano servizi offerti dai server
- **p2p**: ogni nodo può assumere dinamicamente il ruolo di client o di server
- **pipeline**: catena di elementi computazionali costruita in modo tale che l'output dell'i-esimo elemento sia l'input dell'(i+1)-esimo
- **multi-tier**: architettura c/s in cui le applicazioni sono eseguite da più agenti sw diversi
- **blackboard**: sfrutta una base di conoscenza comune, che è aggiornata iterativamente da diverse fonti di conoscenza. Funge da mezzo di sincronizzazione e facilita il decoupling in tempo e spazio.
- **pub/sub**: sfrutta un Event Channel per la pubblicazione di contenuti e un Notifier per avvisare della presenza di nuovi messaggi (astrae dalla posizione/distribuzione del broker). Alcuni modelli pub/sub garantiscono decoupling, alcuni no