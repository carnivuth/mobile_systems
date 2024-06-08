# MOBILE MIDDLEWARE

**Definizione generale di MW**: stack di supporto cross-layer e application-agnostic, che mira a problemi e sfide dei livelli OSI >= 4 (sessione, trasporto, presentazione e applicazione).

Il MW deve essere **riutilizzabile** in varie applicazioni

La nozione classica di MW non è adatta ad ambienti mobili, per via di:
- disponibilità energetica e risorse limitate;
- mobilità dei nodi.

Il ***==mobile middleware==*** si pone come obiettivi:
- fault tolerance;
- adattabilità;
- scalabilità;
- supporto all'eterogeneità;
- condivisione delle risorse;
- visibilità delle condizioni di esecuzione ai livelli inferiori, perché nel mobile MW i livelli sono collegati in termini di coordinazione e visibilità (mentre nel MW in OSI i livelli sono separati).

Inoltre, c'è la necessità di effettuare *decoupling in space & time* per via delle variazioni dinamiche del contesto, dovute alla mobilità stessa dei nodi. A questo scopo si utilizzano dei ==*proxy*==

Nella progettazione delle applicazioni si adotta un **MODELLO A CLESSIDRA**:
- in **basso** abbiamo dispositivi eterogenei (= layer fisici diversi);
- al **centro** abbiamo il livello di trasporto (TCP/IP), convergenza;
- divergenza in **alto**, con applicazioni con bisogni differenti.
![](Pasted%20image%2020240608112155.png)