# Time of Arrival

Tecnica usata in GPS. La distanza viene calcolata con la formula $d = v_s * ToA$, dove:
- $v_s$ è la velocità di propagazione del segnale;
- $ToA$ è il Time of Arrival, cioè il tempo che il segnale impiega per andare dal trasmettitore al ricevitore

Il Tx (in GPS, tipicamente un satellite) invia al Rx (es. uno smartphone) un segnale con il proprio timestamp, così che Rx possa calcolare il tempo di arrivo (tipicamente $ToA = timestamp_Rx - timestamp_Tx$).

![](Toa.png)

Non si usano meccanismi come il Round Trip Time in GPS (quindi un meccanismo di ACK), semplicemente perché il dispositivo consumerebbe troppa energia nel mandare l'ACK al satellite.

**Svantaggi**
- il clock di Tx e Rx deve essere ***perfettamente sincronizzato***, altrimenti ci sarebbero errori nel calcolo della distanza