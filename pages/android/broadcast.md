# BROADCAST

Messaggi inviati dal sistema Android **quando si verifica un evento di particolare interesse**.
Sono wrappati in un oggetto Intent, che contiente i dettagli dell'evento (es. quando collego/scollego gli auricolari, viene inviato il mesaggio *android.intent.HEADSET_PLUG*).

Due tipi di broadcast:
1) **Sistema**: inviati dal sistema Android e sono utili in quei contesti in cui si vuole notificare il sistema o un'applicazione, affinché venga eseguita un'azione particolare (es. *ACTION_BOOT_COMPLETED* o *ACTION_POWER_CONNECTED*)
2) **Custom**: possiamo definirli noi per le nostre app e si comportano similmente a quelli di sistema. L'Activity mittente ed il Broadcast Receiver devono **concordare un nome unico per l'Intent**, così da limitare la visibilità del broadcast ai ricevitori che ne riconoscono il nome
   Ci sono 3 modi per inviare un broadcast:
	   - **ORDERED BROADCAST** (variante sequenziale del pub/sub): si invia ad un ricevitore alla volta, in base alla priorità definita dall'attributo *androir:priority*. I ricevitori possono propagare il risultato al ricevitore successivo o **abortire il broadcast**. I ricevitori con pari priorità sono serviti in ordine arbitrario.
	   - **NORMAL BROADCAST** (pub/sub): ricevuto da tutti i ricevitori registrati, in un ordine predefinito. I ricevitori non possono né propagare i messaggi, né abortire il broadcast (più efficiente).
	   - **LOCAL BROADCAST**: consegnato ai ricevitori specifici di un'applicazione. Non c'è alcun problema di sicurezza, perché processi diversi non comunicano. Utili quando si vogliono innescare particolari comportamenti all'interno della propria app.

È cosa buona e giusta limitare i broadcast alla propria applicazione, perché non farlo può portare a problemi di sicurezza (app potrebbe condividere info sensibili) e aumento di overhead. Se possibile, meglio utilizzare un `LocalBroadcastManager`, che mantiene i dati all'interno dell'app. Importante è l'utilizzo dei permessi.

#### Permessi di accesso al broadcast

- **Invio broadcast** --> Vengono imposti fornendo un parametro di permesso non nullo a `sendBroadcast()`: solo i ricevitori che richiedono questo permesso (usando il tag `<uses-permission>` nel manifest) possono ricevere il broadcast
- **Ricezione broadcast**
	- **In caso di registrazione dinamica** --> fornire permesso non nullo a `registerReceiver()`
	- **In caso di registrazione dinamica** --> usare l'attributo `android:permission` all'interno del tag `<receiver>` nel manifest.

# BROADCAST RECEIVER

Vengono creati usando la classe `BroadcastReceiver` e sovrascrivendo il metodo `onReceive()`. Successivamente, si registrano ai broadcast a cui sono interessati e vengono notificati tramite un Intent broadcast dal sistema o da un'altra app. 

Due tipologie di registrazione:
- **Statica**, tramite specifica degli Intent Filter nel manifest
- **Dinamica**: i broadcast receiver si registrano sfruttando opportune API poste al loro interno per specificare gli Intent Filter.
Gli intent filter specificano i tipi di Intent che un ricevitore broadcast può ricevere. Per aggiungerne uno al manifest si usa il tag `<intent-filter>`, mentre per aggiungerlo al codice Java si usa l'oggetto `IntentFilter.`


