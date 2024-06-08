# LAZY ACQUISITION

A volte non si può predire quali risorse saranno utilizzate a run-time; quindi, per ottimizzare l'uso delle risorse, cercando di posticipare il più possibile la loro acquisizione.

<<<<<<< Updated upstream
Essa sfrutta un **==Resource Proxy==**, che si occupa di intercettare le richieste di accesso alle risorse da parte dell'utente: non acquisisce le risorse finché l'utente non vi accede esplicitamente.
=======
Essa sfrutta un **==Resource Proxy==**, che si occupa di intercettare le richieste di accesso alle risorse da parte dell'utente: non acquisisce le risorse finché l'utente non vi accede esplicitamente.

**Esempio:**
Supponiamo di avere nella cache una copia di una risorsa e di apportare modifiche frequenti alle informazioni contenute in essa. Le modifiche non interessano la risorsa vera e propria, che si trova in remoto, ma la nostra copia locale, così da non invalidare le cache di altri client. Solo alla fine (es. terminazione della sessione), si aggiorna la risorsa effettiva.

Questo limita il numero di accessi da remoto, ma potrebbe introdurre delle problematiche relative all'accesso concorrente ad una risorsa da parte di più client.
>>>>>>> Stashed changes
