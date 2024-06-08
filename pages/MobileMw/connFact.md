# CONNECTION FACTORY

Si disaccoppiano applicazione e sistema di comunicazione sottostante tramite la **connection factory**, un componente che istanzia, accede e termina le connessioni. 

Quindi, il programmatore non crea direttamente le connessioni, ma le istanzia tramite la connection factory, così da gestire in maniera più efficiente il codice e da riutilizzare le connessioni.

Questo pattern è utilizzato dalle API per JavaME