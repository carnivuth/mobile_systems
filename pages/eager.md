# EAGER ACQUISITION

Variante del caching che permette di velocizzare il bootstrap e l'esecuzione, effettuando il **prefetch di alcune risorse quando l'applicazione viene avviata**. Così facendo, le risorse sono **già disponibili localmente** quando se ne ha effettivamente bisogno e non c'è nessuna necessità di fare richieste remote.

#### Eager vs Caching

- il **==caching==** si concentra sui contenuti;
- **==eager acquisition==** si concentra sulle risorse necessarie a runtime