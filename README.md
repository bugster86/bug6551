Descrizione
=========
Il role risolve il bug 6551 presente in bugzilla.
Posiziona il file  di configurazione di opensips presente alla revisione SVN 14856 dell'uRL http://svn/repos/CT6/branches/7.0.4/procs/x2xSipRouter/cfg

Requisiti
=========
L'esecuzione del playbook fallisce se:
* Non viene passato il parametro DB
* Non è presente lo strato redis sul parco macchine su cui viene applicato il playbook


Variabili da passare
--------------

DB --> Nome dell'host ansible in cui è presente l'istanza master di mysql

Dipendenze
------------
Per avere a disposizione lo strato redis correttamente configurato, sul sistem deve essere precedentemente applicato il playbook role 6315


Esempi di utilizzo
----------------

ansible-playbook -l <elenco tutti gli hosts di un cliente> -C /home/playbook/bugs/6551/main.yml -e DB=<server che ha ruolo di DB master>
ansible-playbook -l <elenco tutti gli hosts di un cliente> /home/playbook/bugs/6551/main.yml -e DB=<server che ha ruolo di DB master>

Il primo comando esegue l'operazione in dry run e il secondo applica effettivamente l'operazione

Autore
------------------
Martino Viganò
Martino.Vigano@enghouse.com
