# TASK

I task modellano le interazioni tra Activity, che sono gestite tramite uno stack LIFO: in cima c'è l'unica activity in `RUNNING`. Quando un'activity viene lanciata, viene messa in cima allo stack (*push*), mentre quando termina viene tolta (*pop*), così che l'activity "dietro" di essa possa ritornare in cima.
Quando premiamo il pulsante "Home", ci muoviamo tra task diversi, ovvero tra app e home.

![](Pasted%20image%2020240610105648.png)