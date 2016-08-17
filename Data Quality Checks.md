In questo wiki vanno collezionate tutte le regole che devono essere soddisfatte in fase di importazione delle anagrafiche prodotto in 
modo che i prodotti possano poi essere venduti online.

Elencare sempre il nome del dato da verificare (tabella principale) e la regola utilizzando possibilmente i campi degli oggetti java:

Prodotto:
se product.productInfos.TIPOLOGIA=="Sfuso" --> 
product.productInfos.STEP_SELLING o product.productInfos.WEIGHT_SELLING devono essere valorizzati ed essere numeri


