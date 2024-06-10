# JOB SCHEDULER

Usato per la programmazione intelligente dei task pesanti in background.
È basato su **condizioni** ed è molto più efficiente di un AlarmManager. 
Inoltre, Android **raggruppa assieme gli scheduling dei task** per **minimizzare il consumo** della batteria.

Si ha a disposizione:
- **JobService**: servizio in cui viene avviato il task. Gira sul main thread e richiede l'override di:
	- `onStartJob()` --> gira sul main thread ed è chiamato dal sistema quando le condizioni sono soddisfatte. Delega i compiti più pesanti ad un altro thread, il quale dovrà chiamare il metodo `jobFinished()` al termine. Restituisce FALSE se il job è terminato, o TRUE se è stato delegato.
	- `onStopJob()` --> chiamato se il sistema Android ha determinato che l'esecuzione del task deve fermarsi, perché le condizioni non sono più soddisfatte. Prima di fermare, si chiama `jobFinished(JobParameters, boolean)`, per passare i parametri ed aggiornare lo stato interno. Permette di riprogrammare i task.
- **JobInfo**: per impostare le condizioni di esecuzione del task. Ha come argomenti l'ID del job, il Service che esegue il JobService ed il JobService stesso.
  **Condizioni settabili**:
	  - latenza minima;
	  - periodicità di esecuzione;
	  - tipologia di rete richiesta;
	  - tipo di alimentazione/check se il dispositivo è in carica o meno;
	  - etc.
- **JobScheduler**: per fare lo scheduling dei task. Si ottiene un *JobScheduler* dal sistema e si chiama *schedule()*, con l'oggetto *JobInfo*.