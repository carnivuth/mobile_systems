# PRINCIPI INTERNET

Abbiamo due principi:
1) **End-to-End principle** --> si mantiene stato e intelligenza solo sugli end-point comunicanti. TUTTAVIA, negli scenari reali abbiamo firewall, Network Access Traversal, cache per contenuti Web, che non sono adatti a questo principio.
   
2) **Principio di robustezza** --> *"Be conservative in what you do, be liberal in what you accept from others"*. Ciò vuol dire che gli sviluppatori di stack Internet devono **rispettare quanto specificato nelle RFC**, ma **essere pronti ad elaborare in modo più elastico e ad accettare input non conformi** provenienti dall'esterno.
   Permette una **compatibilità più alta** tra domini eterogenei.
