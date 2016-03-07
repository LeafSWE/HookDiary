# HookRepo
In questo repository sono contenuti il file di hook e il file diaryGenerator.

##Requisiti
1. Perl
2. Modulo libXML di Perl
3. Deve essere presente il file diaryGenerator.perl
4. In ogni cartella dei vari documenti devono essere presenti 2 file:
    1. .registroModifcheXX.xml (dove XX è la sigla di un documento in maiuscolo)
    2. diarioModificheXX.tex (dove XX è la sigla di un documento in maiuscolo)

##Che cosa fa
1. Dopo ogni commit chiede:
    1. Se si vuole generare il diario
    2. Che documento è stato modificato con il commit
    3. Quale ruolo si ha all'interno del gruppo
    4. Se si vuole fare l'upgrade della versione, ovvero passare da 1.xx a 2.00 e così via
2. Vengono cercati i file da modificare e vengono passati tutti i dati allo script Perl diaryGenerator.pl
3. Lo script:
    1. aggiorna il file .registroModifche.xml
    2. Da .registroModicheXX.xml viene generato il nuovo file diarioModificheXX.tex
4. Viene ricompilato il documento che è stato modificato 2 volte, in modo da evitare problemi con gli indici
5. Viene generato un commit automatico che contiene i file appena modificati.
6. Il documento adesso è aggiornato e il file PDF contiene il diario aggiornato con il messaggio dell'ultimo commit.
