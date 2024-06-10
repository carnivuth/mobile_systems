# SICUREZZA

Linee guida di sicurezza in Linux.
Di default, ogni applicazione è eseguita in una Dalvik VM dedicata, e all'interno di un proprio processo separato.
Ad ogni app è associato:
- **user ID**;
- **group ID**;
che sono selezionati da un intervallo definito a livello di sistema: $FIRST_APPLICATION_UID - LAST_APPLICATION_UID$.
I **permessi** sono stabiliti a seconda dello user ID e del group ID e possono esserne concessi di più specifici, andando a **dichiararli nel manifest**.