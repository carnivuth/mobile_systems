# REMOTE FACADE

Un dispositivo mobile effettua richieste ad un singolo **entry point**, detto *==facade==*.
La *facade* comunica con diversi servizi esterni e restituisce dei risultati al client

#### Vantaggi
1) decoupling tra Client e Server
2) il client può avere differenti protocolli di comunicazione, mentre il server agisce da **gateway remoto**, che trasforma le richieste del client nello standard usato dai servizi
3) semplice protocollo di *request/response* --> comunicazioni asincrone --> no problemi relativi alle disconnessioni
4) il client non deve conoscere quali server o funzioni sono utilizzate per implementare le operazioni richieste.