# ANDROID MIDDLEWARE

Esistono diverse proposte per lo sviluppo di ambienti di sviluppo/runtime per sistemi mobili, per via dell'eterogeneità di questi ultimi. Tra tutti, i più importanti sono iOS e ==Android==.

Spesso ci si riferisce ad Android come un Sistema Operativo, ma questa definizione è spesso inesatta. Infatti, oltre che su un [kernel Linux-based](kernel.md), poggia su altri 4 *layers*:
- ==**Librerie native**==: alcuni componenti fondamentali sono implementati in C/C++ per migliorare le prestazioni. Esempio: stack multimediale.
- **==Android Runtime==**: Nei classici S.O., si può scrivere del codice in un qualsiasi linguaggio di programmazione ed eseguirne l'exe senza problemi. Inoltre, il codice può anche presentare errori/loop. ==In Android, questo non è possibile==. Infatti, siamo vincolati a scrivere SOLAMENTE applicazioni scritte in una versione Java Android-compliant, che verranno eseguite dal supporto al runtime, che è PARTE del mobile MW di Android. Inoltre, alcune soluzioni potrebbero imporre l'esecuzione di app come se fossero delle VM (Dalvik VM o ART), o dei container Docker, o in altre forme. Nello specifico, l'Android Runtime è un ambiente di esecuzione per le applicazioni, scritto in Java Android-compliant e basato su Dalvik VM, ovvero la VM che esegue le applicazioni.
- ==**Android Framework**==: fornisce applicazioni con servizi avanzati, mediante delle classi (oggetti) scritte(i) in Java Android-compliant. Sono messe in esecuzione dal supporto di Android; quindi, non puoi scegliere se eseguirle o meno: quella è una decisione che spetta al mobile MW.
- ==**Application**==: applicazioni native fornite dal sistema o sviluppate dai programmatori.

#### Versioni

Negli anni si sono susseguite tante versioni, in cui si è limitata sempre più la libertà concessa agli utenti, in modo tale da fornire un prodotto sempre più stabile e sicuro.
Tra i vari update effettuati, elenchiamo quelli più importanti:
- Da Lollipop 5.0 (2014), Dalvik VM è stata sostituita da Android RunTime (ART).
- In Nougat (2016), è stato fornito supporto alla visualizzazione di più app contemporaneamente su schermo.
- In Android 10 (2019), sono state introdotte le Notification Bubbles, così che i componenti principali del SO si aggiornassero tramite Play Store, senza aggiornare completamente il sistema ogni volta.