# ALARM

Componente che **fa scattare l'esecuzione di certe operazioni ad orari prestabiliti, inviando degli Intent**. Può scattare:
- una sola volta;
- periodicamente.
Si basa su uno tra:
- orologio in tempo reale (**Real Time Clock - RTC**);
- tempo trascorso (**Elapsed Real Time - ERT**).

![](Screenshot%202024-06-10%20143244.png)

*ESEMPIO*: supponiamo di avere un'applicazione con milioni di utenti, che ha bisogno di aggiornarsi/sincronizzarsi con un server.
- In Alarm RTC con risveglio (1), si avrebbe un enorme numero di richieste contemporanee al server e conseguenti problemi: tutti i dispositivi verrebbero svegliati nello stesso momento.
- ERT senza wake up (2) è la più vantaggiosa, perché possiede due elementi di randomizzazione, che ci rendono sicuri del fatto che le richieste di aggiornamento avverranno in intervalli differenti:
	  1) non tutti accendiamo lo smartphone nello stesso momento;
	  2) non tutti lo svegliamo nello stesso istante.
- I casi (3) e (4) sono vie di mezzo, che possiedono solo uno dei due elementi di randomizzazione di cui sopra.

**COME FUNZIONA?**
Un Alarm viene utilizzato in combinazione con i [BroadcastReceiver](broadcast.md):
1) un'activity crea una notifica e setta un Alarm;
2) l'Alarm scatta e invia l'Intent;
3) il BroadcastReceiver sveglia l'app e consegna la notifica;
4) la notifica appare a schermo.

Si sveglia la CPU anche se lo schermo è spento **solo per operazioni critiche**, perché questa è una pratica che consuma velocemente la batteria. Per altri tipi di operazioni, l'Alarm scatterà non appena esso verrà svegliato.

![](Pasted%20image%2020240610141301.png)

**Vantaggi**:
- non è necessario che l'app sia in esecuzione o che il dispositivo sia sveglio affinché l'Alarm viene attivato a runtime;
- l'Alarm non utilizza risorse finchè non scatta.

Per **ridurre al minimo il risveglio** del dispositivo **negli allarmi ripetuti**, si può utilizzare il metodo `setInexactRepeating()`, che fa scattare un singolo Alarm nel caso in cui l'intervallo di tempo fra due o più Alarm ripetuti sia relativamente piccolo (fa scattare più Alarm simmultaneamente con uno solo). Altrimenti, di default si usa `setRepeating()`, che fa svegliare il dispositivo ad ogni Alarm, cioè più del necessario.

**Accorgimenti**:
- **meglio non usare gli Alarm**, preferendogli meccanismi di timeout, degli Handler o delle richieste push da Cloud;
- si potrebbe inviare le **richieste di aggiornamento di notte**, perché di solito non si utilizzano i dispositivi.

**Pianificazione Alarm**
Dobbiamo prima di tutto sapere il **tipo di Alarm**, **quando farlo scattare**, l'eventuale **intervallo di ripetizione** e **l'Intent da inviare** quando scatta.

- **singolo alarm**
	- *set()* --> singolo allarme inesatto
	- *setWindow()* --> singolo allarme inesatto, ma all'interno di una finestra temporale
	- *setExact* --> singolo allarme esatto
- **alarm ripetuto**
	- *setInexactRepeating()* --> allarme inesatto ripetuto
	- *setRepeating()* --> allarme esatto ripetuto (questo fino a API 19, dopo è simile al precedente)
