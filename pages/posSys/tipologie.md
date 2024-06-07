# TIPOLOGIE DI posSys

- **FISICI** --> restituiscono valori numerici (longitudine e latitudine). No privacy, perché chi le ottiene sa dove mi trovo di preciso;
- **SIMBOLICI** --> restituiscono posizioni simboliche a livelli, più comprensibili all'essere umano e più veloci da elaborare. Inoltre, la privacy è maggiore, perché non si sa con precisione dove mi trovo;
- **ASSOLUTI** --> la precisione viene riferita ad *un solo sistema di localizzazione*;
- **RELATIVI** --> la posizione di un dispositivo si riferisce a *quella di un altro dispositivo*. 
- **CENTRALIZZATI** --> c'è un server centrale che determina le posizioni di tutti i dispositivi. Minor privacy, perché per poter determinare le posizioni, spesso deve salvare le info sui dispositivi da qualche parte (es. db, quindi un criminale potrebbe fare data breach)
- **DECENTRALIZZATI** --> i vari dispositivi auto-determinano le proprie posizioni (ad esempio, usando GPS). Maggior privacy, perché solo lo specifico nodo ha le info sulla sua posizione.