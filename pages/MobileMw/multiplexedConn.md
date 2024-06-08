# MULTIPLEXED CONNECTION

Dato che risulta inefficiente creare tante connessioni, che poi vanno a competere per l'accesso alle risorse di rete/di sistema, si può sfruttare una **singola connessione logica**, condivisa tra più client tramite **connessioni multiple** a livello applicativo. Ciò ci permette di avere **priorità differenziate** per i messaggi.

Un esempio è lo Stream Control Transfer Protocol (SCTP), in cui si controlla lo stream video/audio tramite comandi come "avanti veloce"/"stop"/"play"/etc, i quali vengono inviati **insieme** allo stream dati.