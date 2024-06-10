# TECNICHE ASINCRONE

#### 1) Service

Componente dell'applicazione che esegue operazioni di lunga durata in background:
- no interazione con l'utente;
- non aggiorna la UI (ne è scollegato);
- MA di default esegue sul *thread UI* (*main thread*).
Sono attivati da Intent e possono servirsi di *worker thread*, a cui delegano dei compiti, così da evitare il blocco del main thread (quindi dell'app), qualora un Service non dovesse rispondere.
Non possono accedere alla UI: per mostrare i risultati si usano i BroadcastReceiver e gli AsynchTask.

Abbiamo 3 tipi di Service:
1) **Unbounded/Started Service**: rimangono in esecuzione infinitamente, finché non si arrestano da soli --> Il loro lifecycle va gestito dal programmatore: se non vengono fermati, rimangono in loop e consumano inutilmente risorse. Possono fermarsi da soli (`stopSelf()`) o essere fermati da un altro componente (`stopService()`).
2) **Bounded Service**: interfaccia C/S, in cui i client richiedono ed ottengono risultati al servizio. Permette ai vari componenti del sistema di interagire col Service e termina quando tutti i client si sono scollegati.
3) **Foreground Service**: sono sempre eseguiti in background, ma richiedono che gli utenti sappiano della loro esistenza. Questo perché devono fornire agli utenti una notifica non eliminabile durante l'esecuzione del servizio, sia per motivi di sicurezza, sia per risparmio energetico (si capisce quali applicazioni stanno consumando risorse). Possiedono una priorità più alta rispetto ai Service in background.

**CREAZIONE DI UN SERVIZIO**
- lo dichiaro nel manifest;
- gli fornisco i permessi necessari ad espletare le sue funzioni;
- lo istanzio tramite *IntentService* o *Service*;
- implemento i metodi da chiamare a runtime;
- mi assicuro che sia arrestabile;
- lo avvio dall'activity.

#### 2) IntentService

Semplifica il mgmt del lifecycle di un Service:
- sfrutta i *worker thread* per soddisfare le richieste,
- si ferma da solo quando ha finito;
- ideale per lunghe operazioni in background.

Limitazioni:
- non può modificare la UI;
- soddisfa una richiesta alla volta;
- non può essere interrotto.

#### 3) Thread

Come i normali thread in Java, MA **non possono interagire sugli oggetti dell'interfaccia utente**, poiché il toolkit UI non è thread-safe. Quando si è progettato il sistema Android, si è pensato di avere una sola Activity in stato di `RUNNING`; quindi, non è stata implementata la modifica/l'aggiornamento concorrente della UI.

I thread non possono essere fermati con i metodi `destroy()` o `stop()`, ma con opportuni metodi in base alle circostanze: `interrupt()` o `join()`.

Esistono **due metodi** per avere un thread che esegue il codice di un'app:
1) fornire una **nuova classe `Thread`** e sovrascrivere il suo metodo `run()`;
2) fornire una **nuova istanza di `Thread`** con un oggetto `Runnable` durante la sua esecuzione.

In entrambi i casi, si chiama esplicitamente il metodo `start()` per eseguire il thread.

#### 4) Handler

 L'handler è un altro metodo per gestire il multi-threading: crea un **canale di comunicazione tra il main thread ed un nuovo thread**, al quale viene associato insieme ad una **coda di messaggi** (FIFO). 

**COME FUNZIONA?** L'handler riceve i messaggi e i runnable  e li consegna alla coda, così da eseguirli man mano che escono.

Gli handler hanno due modalità di utilizzo:
1) per programmare i messaggi e i runnable da usare in futuro;
2) per aggiungere un'azione in una coda che verrà eseguita su un altro thread

#### ==5) ASYNCTASK==

Servono per interagire con la UI. Vengono creati sul thread UI ed eseguiti una sola volta in un thread in background. Possono anche aggiornare la UI, per mostrare i risultati ottenuti.

Tre parametri da passare agli AsyncTask:
- **Params**: tipo di parametri passati all'AsyncTask;
- **Progress**: unità di misura della barra di progresso
- **Result**: tipo di risultato del calcolo fatto in background.

Quattro **metodi di callback** per il lifecycle mgmt degli AsyncTask:
-  `onPreExecute`: eseguito dal thread UI (quindi può modificare la UI) dopo l'avvio dell'AsyncTask, per prepararlo all'esecuzione delle operazioni. 
- `doInBackground(Params ...)`: è invocato dopo `onPreExecute` da un thread in background (che opera in // col thread UI; quindi, non può aggiornare la UI), su cui esegue la logica applicativa.
- `onProgressUpdate(Progress ...)`: è invocato dal thread UI per aggiornare l'andamento dell'AsyncTask. Può modificare la UI (es: mostra progress bar).
- `onPostExecute(Result ...)`: invocato dal thread UI per ottenere i risultati e rilasciare le risorse allocate all'AsyncTask.