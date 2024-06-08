# LAZY ACQUISITION

A volte non si può predire quali risorse saranno utilizzate a run-time; quindi, per ottimizzare l'uso delle risorse, cercando di posticipare il più possibile la loro acquisizione.

Essa sfrutta un **==Resource Proxy==**, che si occupa di intercettare le richieste di accesso alle risorse da parte dell'utente: non acquisisce le risorse finché l'utente non vi accede esplicitamente.