# STATE TRANSFER

Il **rendez-vous** è un pattern simmetrico per la sincronizzazione, usato per la gestione dei dispositivi mobili. In generale, **permette a due o più entità di sincronizzare le loro attività**. Tipicamente è implementato tramite **punti di rendez-vous**, cioè entità logicamente centralizzate che accettano msg/pacchetti e **mantengono lo stato**; quindi, sono in grado di **rispondere sempre alle richieste dei client**.

Esempio:

![](Pasted%20image%2020240608191200.png)

I client A e B sono entità possibilmente mobili. Il punto di rendez-vous è un'entità fissa (o poco mobile) e nota a priori ai client.


##### S.T. & handoff

Esistono diversi tipi di handoff, che possono richiedere un **trasferimento di stato** tra gli AP. --> Si possono sfruttare i punti di rendez-vous a questo scopo: il client che è connesso al vecchio AP e vuole connettersi ad uno nuovo, aggiorna il suo stato sul punto di rendez-vous e si connette al nuovo AP. Il correspondent node interagisce con il punto di rendez-vous per conoscere lo stato del client e poterci communicare.

![](Pasted%20image%2020240608191524.png)