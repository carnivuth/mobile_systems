# DATA TRANSFER OBJECT

Sfrutta un oggetto serializzabile, detto ***container***, per contenere i dati da inviare ad un dispositivo remoto. Il container include un insieme di campi con corrispondenti metodi *getter* e *setter*.

#### VANTAGGI
1) riduzione del numero di chiamate a metodi remoti (non effettuo una RMI per ogni tipo di dato da trasferire)