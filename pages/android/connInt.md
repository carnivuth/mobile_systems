# CONNESSIONE A INTERNET

Perché un'applicazione Android possa connettersi ad Internet o per effettuare controlli sullo stato di rete, è necessario **dichiarare i relativi permessi nel manifest**.

Ci si connette a Internet tramite il `ConnectivityManager`, che risponde alle domande sullo stato di rete e notifica alle app quando la connettività cambia.
Il `NetworkInfo` descrive lo stato di una connessione, ad esempio Mobile o WiFi.

![](Pasted%20image%2020240610150926.png)![](Pasted%20image%2020240610150937.png)

**Scaricare dati in background**
- operazioni brevi --> AsyncTask
- operazioni lunghe --> AsyncTaskLoader, che restituiscono anche dei risultati alla UI o dei background services.
In ogni caso, nei task in background dobbiamo:
1) creare un URI;
2) stabilire una connessione HTTP;
3) scaricare i dati.

**Creazione di connessioni di rete**
Si può:
- Usare `HttpURLConnection`, che va eseguito su un thread separato e richiede l'istanziazione di un `InputStream`.

![](Pasted%20image%2020240610151231.png)

- Usare **librerie esterne** (OkHttp o Volley), che devono essere chiamate nel main thread e permettono di scrivere meno codice.

**Ricezione dati**
Bisogna implementare il metodo [`onPostExecute()`](tecAsynch.md). Poiché le risposte sono solitamente dei JSON o XML, bisogna parsarle tramite degli *helper* (es. `JSONObject`, `JSONArray` o `XMLPullParser`)

**Trasferimento dati efficiente**
L'**interfaccia radio** può operare:
- *piena potenza* --> connessione sempre attiva, max velocità;
- *bassa potenza* --> utilizza il 50% di energia in meno;
- *standby* --> minimo consumo di energia, nessuna connessione attiva.

Android cerca di **impacchettare i dati**, facendone il **prefetch**, cioè scaricando tutti i dati di cui si ha *probabilmente* bisogno in un **singolo burst alla max velocità**:
- meno trasferimenti;
- consumo energetico ridotto, perché l'interfaccia rimane per più tempo in idle;
- meno latenza.

Posso determinare quale interfaccia radio è attiva con il `ConnectivityManager`, così da adottare policy diverse a seconda delle necessità.