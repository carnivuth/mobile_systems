# CICLO DI VITA DELLE ACTIVITY

Ci sono molte *activity* simmultaneamente in esecuzione, ma quella **attiva** (`RUNNING`) è solo quella con cui sta interagendo l'utente.
Quando si avvia un'app, parte il lifecycle management e Android invoca i metodi `OnCreate()` e `OnStart()`: ora l'activity è in stato di `RUNNING`. Mentre è in tale stato, essa attende un input da parte dell'utente.
L'activity può essere messa in pausa tramite il metodo `OnPause()`: non è attiva, ma è visibile in primo piano (a finestra ridotta). Il thread che eseguiva tale activity non viene più utilizzato da essa e passa ad un'altra activity, quella attualmente in `RUNNING`.
Inoltre, può essere è `STOPPED` (`OnStop()`): non è né attiva, né visibile. Prima di mettere in pausa l'activity, possiamo salvarne lo stato in un contenitore, detto **Bundle**, col metodo `OnSaveInstaceState(Bundle)`. Per ripristinare lo stato dell'activity quando viene rimessa in running (`OnResume()`), si usa il metodo `OnRestoreInstanceState(Bundle)`.
Se mancano le risorse necessarie all'activity, potrebbe essere deallocata (`KILLED`, metodo `OnDestroy()`): tipicamente si deallocano prima le activity meno prioritarie (prima STOPPED, poi PAUSED), così da riservare tutte le risorse necessarie all'activity in `RUNNING`.

Il lifecycle mgmt è fatto in automatico dal runtime di Android.

![](Pasted%20image%2020240610100558.png)