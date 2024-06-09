# SESSION TOKEN

Un token viene emesso dal server ed inviato al client, e serve ad associare quest'ultimo ad una sessione.
Nel token sono presenti:
- session ID;
- info di sicurezza relative alla sessione;
- stato della sessione;
- TTL, per evitare attacchi di replay.

Quando il client ripresenta il token al server, quest'ultimo associa il client alla corrispondente sessione in maniera univoca e continua a fornirgli il servizio.

#### VANTAGGI
1) no problemi relativi alla mobilità dei nodi (quindi cambio IP e locazione);
2) alleggerisce compiti e requisiti per la gestione dello stato di sessione lato server.