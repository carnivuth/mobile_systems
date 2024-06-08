## Meccanismi di base

Un meccanismo di base spesso usato è il **==versioning==**, che adotta un approccio ottimistico. In ogni locazione, i **numeri di versione** relativi a una risorsa **aumentano progressivamente ad ogni modifica**. I meccanismi di *versioning* soddisfano le seguenti proprietà:
1) se la versione B deriva da un cambiamento di A, allora $num(B) > num(A)$
2) se due copie sono state modificate simultaneamente in luoghi diversi, allora i numeri di versione non sono comparabili. I numeri di sequenza servono a creare una sequenza lineare di versioni all'interno di una singola locazione, ma due versioni provenienti da due locazioni diverse non possono essere confrontate
   Es: A genera una versione 2 e B genera una versione 4 --> Non posso dire che v4 è meglio di v2, perché sono di due entità diverse.

Per quanto riguarda il versioning, abbiamo le seguenti fasi:
- **propagazione degli aggiornamenti**;
- **rilevamento delle modifiche**;
- **riconciliazione** 
	- tramite log delle operazioni della modifica --> si elabora il log complessivo partendo dall'ultima versione comune prima dei cambiamenti;
	- tramite gli stati dei dati modificati --> opera direttamente sui dati modificati.

Nei casi reali, la sincronizzazione avviene **esclusivamente fra coppie di nodi**, adottando tre tipi di architetture:
- **CENTRALIZZATA**: un nodo master per ogni dato. I nodi operano su copie del dato e devono sincronizzarsi con il master
- **AD ALBERO**: un master radice per ogni dato, sotto-alberi che si occupano delle copie del dato e le foglie che utilizzano tali copie. La sincronizzazione procede dalle foglie verso il master (dal basso verso l'alto)
- **A GRAFICO CICLICO CONNESSO**: 
	- più generale
	- maggiore flessibilità
	- gestione più complessa, perché non si sa quali versioni considerare per la comparazione di stato
	- raramente usata nei sistemi moderni
Infine, gli algoritmi di riconciliazione possono beneficiare della conoscenza della struttura dei dati condivisi e dei servizi offerti dall'applicazione.