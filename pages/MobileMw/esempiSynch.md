# Esempi 

#### 1) FS distribuiti (DFS/NFS)

- In DFS, alcune parti del FS sono sia remote che locali e sono distribuite su molti nodi 
  --> necessità di sincronizzare le parti quando le copie locali devono essere allineate con le remote + intervento dell'utente per risolvere eventuali conflitti.

- In NFS si ha un **server stateless**, che mantiene una porzione di FS. I client accedono a questo server per operare sui dati e posseggono uno stato in cui salvare su che punto del file stanno leggendo/scrivendo. Non c'è un forte bisogno di sincronizzare, perché i client modificheranno le risorse direttamente sul server.

#### 2) Concurrent Versions Systems (CVS)

Sfruttano la sincronizzazione a livello di dati.
Le prime implementazioni prevedevano un **server centralizzato** che rilasciava un lock ad un solo client alla volta per accedere in scrittura al file.
Ora si usa un approccio ottimistico, con architettura decentralizzata in cui ogni membro del team può lavorare sulla sua copia in locale e riconcilia le eventuali differenze (es. GitHub).

Nei sistemi mobili per la sincronizzazione di mail/DB, lo standard è Synchronization Markup Language (SyncML).
