# CACHING

Dopo che il client utilizza una risorsa, la salva temporaneamente in una cache, così che quando ne avrà nuovamente bisogno andrà a ripescarla da lì. Se poi dovesse verificarsi un *cache miss*, la si riscarica e si accede ad essa localmente, senza interagire col servizio remoto. 

#### VANTAGGI
1) utile durante le disconnessioni, poiché la cache può essere consultata anche offline;
2) limita il numero di accessi in remoto;
3) il sistema è più resiliente in termini di mobilità, consumo energetico, etc.

E' stato usato molte volte dai mobile MW che hanno lo scopo di realizzare un FS distribuito per sistemi mobili.