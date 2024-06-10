# APPLICATION FRAMEWORK

Composto da 4 componenti principali:
1) ==**Activity**==: ogni azione che un utente può compiere attraverso un'interfaccia grafica (di solito corrisponde ad una singola schermata). Un'applicazione è costituita da diverse Activity indipendenti e disgiunte, oppure anche da Activity associate tra di loro. Esse devono essere **semplici e riutilizzabili** [See more](activity_lifecycle.md)
2) [==**Service**==](tecAsynch.md): opera in *background* e l'utente non vi interagisce direttamente. Utilizzabile da più componenti e non ha un processo dedicato.
3) ==**Intent**==: permette di far interagire le varie applicazioni. Per ricevere gli Intent, ci si avvale di un componente che abbia degli *Intent Filter* compatibili, cioè un [*BroadcastReceiver*](broadcast.md).
   Tipicamente, gli Intent sono usati per passare da un'app all'altra e sono di **due tipi**:
	   - **Esplicito**: quando **si sa esattamente la classe del componente da attivare**
	   - **Implicito**: quando **non si conosce tale classe**. Ad esempio, quando abbiamo più app per eseguire un certo compito, il sistema Android ci presenta un menù di scelta, presentando dei componenti selezionati in base ad un algoritmo di *Intent Resolution*, che opera in base agli *Intent Filter* applicabili dichiarati nel manifest. Quindi, l'Intent implicito ha bisogno di specificare:
		   - **azione** da eseguire e **tipo** di componente da attivare;
		   - **uri**, che specifica i dati che il componente attivato deve trattare;
		   - **mime type**, cioè il tipo di dati da utilizzare.
	Ovviamente, se il componente è uno solo, viene attivato direttamente. 
4) ==**BroadcastReceiver**==: riceve e risponde agli Intent compatibili, eseguendo le azioni associate, che tipicamente sono azioni di notifica. Il suo lifecycle è limitato alla singola risposta e, a differenza di Activity e Services, diversi BroadcastReceiver possono essere attivati da un singolo Intent.

Oltre a questi, ci sono altri quattro componenti fondamentali:

1) ==**Package & Activity manager**==, che gestisce il [lifecycle delle activity](activity_lifecycle.md) e delle app incluse nei pacchetti android (**APK**), i quali possiedono una struttura che include:
		- descrittore (o *manifest*);
		- dex eseguibile;
		- risorse statiche associate.
3) ==**Window Manager & View System**==: funzioni grafiche avanzate utilizzabili direttamente nelle applicazioni. View System è basato sulla classe **View** ed è composta da componenti GUI che interagiscono con utente e gestore eventi
4) ==**Resource Manager & Content Provider**==: si occupano di tutte le risorse e dell'accesso condiviso ai dati, tramite db SQLite
5) ==**Telephony, Notification & Location Manager**==