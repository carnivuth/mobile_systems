# LIBRERIE NATIVE

Le librerie native sono scritte in modo tale da essere eseguite efficientemente sul kernel Linux. Sono sviluppate da developer di sistema e non sono modificabili. Sono accessibili tramite opportune API Java. Tipicamente, sono ideate per task pesanti, come grafica e servizi multimediali.


# DALVIK VM

La Dalvik VM è *registry-based*, ovvero sfrutta l'architettura ARM, a differenza della JVM tradizionale, che è stack-based.

- ###### Stack-based vs Registry-based
  
  Le prime hanno una maggiore portabilità, mentre le seconde sono più performanti in termini di velocità di esecuzione e consumo di risorse.

La Dalvik VM interpreta ed esegue i file **dex**, ottenuti con la trasformazione dei file di classe, per ridurre del 30% le istruzioni necessarie e migliorare le performance a runtime. Infine, fornisce supporto alla *garbage collection*
Da Android Lollipop è stata sostituita da ART.