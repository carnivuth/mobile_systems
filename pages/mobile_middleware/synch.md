# SYNCHRONIZATION

Dato che molti dispositivi hanno delle copie locali di una stessa risorsa, bisogna trovare un meccanismo di **sincronizzazione** per evitare inconsistenze nell'aggiornamento della risorsa in remoto, in modo da avere una visione globale dello stato della risorsa. Questo è ottenuto per mezzo di una **synchronization engine**, che rileva e risolve i conflitti durante il processo di sincronizzazione per risolvere le inconsistenze.

Ci sono due tipi di sincronizzazione:
1) **a livello di processo**: i processi agiscono sullo stesso dato e le inconsistenze sono risolte tramite l'imposizione dell'accesso sequenziale per aggiornare le info;
2) **a livello di dati**: i processi lavorano anche offline sulla loro copia locale, e la sincronizzano sul DB periodicamente o in base a determinati eventi (*traveling salesmen scenario*). Per le inconsistenze, è necessaria la *synch engine*. Questa è la tipologia presente nei sistemi mobili. È molto usata perché i casi di conflitti non risolvibili sono molto rari
   
   
![](Pasted%20image%2020240608164230.png)

È possibile fare il merge dei dati durante la sincronizzazione solo nel caso in cui essi non creino inconsistenze o errori logici.

In caso di sincronizzazione bisogna scegliere:
- **quando** lanciare la sincronizzazione;
- **come** sincronizzare, cioè gli *stili di sincronizzazione*:
  
	- **==Pessimistico==**: c'è un'unica copia del dato, che è modificabile, e varie copie in read-only. La sync. è basata sull'allineamento della singola copia modificabile. Approccio non sempre utilizzabile, soprattutto quando si vuole garantire un'esperienza utente fluida
	
		![](Pasted%20image%2020240608175359.png)
	
	- **==Ottimistico==**: multiple copie del dato che possono essere modificate. Sta alla synch engine il garantire la consistenza quando esse verranno sincronizzate. Anche se i due salesmen lavorano in // senza interazioni, riesce a sincronizzare le due copie senza problemi (e senza bloccarli)
	  
	  Ci sono alcuni casi in cui l'*engine* può riscontrare dei problemi. In certi casi si hanno dei conflitti, e l'*engine* può rilevarli *a posteriori*, ma non sono risolvibili automaticamente (supponi che, nella figura qui sotto, il Salesman B non venda 25, ma 60 pezzi. Ormai li hanno venduti, quando l'engine si accorge del conflitto).
	  
	  ![](Pasted%20image%2020240608175912.png)

Quindi praticamente abbiamo dei *gradi di libertà* sullo scheduling della synch engine.