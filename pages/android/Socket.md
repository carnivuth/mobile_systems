# SOCKET

Un **socket** è un'astrazione Java per le connessioni di rete.
In Android abbiamo sia `Socket` lato client che `ServerSocket`, molto simili al Java classico.
Differenze col Java classico:
- permessi da dare per operare a runtime;
- a runtime abbiamo il main thread, quindi non è ottimale aprire il socket nell'activity per utilizzarlo per operazioni lente, poiché si mette in pericolo la responsività dell'app.
Quindi, i socket non sono usati se le operazioni sono lente --> non sono eseguiti sul main thread; quindi, è necessario il multi-threading per parallelizzare main thread e network.

In Android ci sono delle PAI che permettono di configurare i socket a seconda delle necessità del programmatore. Questo perché il nostro smartphone può avere diverse opzioni di connettività; quindi, a seconda delle caratteristiche richieste per il socket, Android può mappare l'astrazione "socket" su una connessione TCP/IP basata su WiFi/5G/LTE/etc.
Quindi, è Android che decide trasparentemente dove va il socket (se su WiFi, 5G o altro).

I socket sono **eseguiti in background** da un *worker thread*. 

Tuttavia, raramente si usa l'astrazione "socket", poiché si tratta di meccanismi di basso livello; quindi, i programmatori usano qualcosa a un livello più alto (es. si mette nell'oggetto Java un'astrazione di connessione TCP/IP o un altro tipo di connessione SW-based) --> è ciò che si fa in Android.