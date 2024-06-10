# THREADING

Android segue il ***single thread model***, in cui ogni app è associata ad un singolo thread, che esegue tutte le Activity che la compongono.
Ogni thread è dotato di un *loop infinito*, per gestire localmente la coda dei messaggi: riceve eventi esterni (di sistema/input dall'utente), che possono essere inviati alle activity.

![](Pasted%20image%2020240610110118.png)

Inoltre, si può:
- eseguire **diverse app in una singola Dalvik VM**: specifico nel manifest uno `sharedUserID`, condiviso da più applicazioni. Questo **ottimizza l'utilizzo delle risorse di sistema**, ma crea un **unico processo pesante** e comporta **potenziali problemi di sicurezza**, poiché le app avranno visibilità completa l'una dell'altra.
- eseguire **ogni app su una Dalvik VM dedicata**: comportamento di default. Maggiore sicurezza, poiché le app sono isolate tra di loro e non hanno visibillità l'una dell'altra. Ovviamente, consumo più risorse.