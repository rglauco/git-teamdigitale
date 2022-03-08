# Italia Community Lab - git
**Comandi di base, valutazione del progetto**
* clone
  * significato: copia localmente l’intera struttura del progetto 
  * scopo: viene utilizzato principalmente per puntare a un repository esistente e creare un clone o una copia di quel repository in una nuova directory, in un'altra posizione
  * esempio: 
    * ```git clone (--depth N  per evitare di portarsi dietro la storia di tutti i commit) https://github.com/consiglionazionaledellericerche/cool-jconon```
* pull
  * significato: sincronizza il repository locale con quello remoto
  * scopo:  incorpora i cambiamenti di un repository nel ramo locale corrente (git fetch + git [merge|rebase] a seconda della configurazione corrente)
  * esempio: 
    * ```git pull https://github.com/consiglionazionaledellericerche/cool-jconon-template```
* log
  * significato: strumento per monitorare la timeline del progetto
  * scopo: comando di ampia portata mostra lo storico delle modifiche
  * esempio: 
    * ```git log --all --graph --decorate --oneline```

**Azioni pre-contributo (elementi di narrazione)**
* apertura issue
* creazione fork su repo personale
* identificare le modalità di contribuzione (PR su branch dev se disponibile)
* commit con messaggio eloquente (vedi sotto)
* apertura PR che referenzia la issue (che chiude la issue automaticamente al merge)
* richiesta revisione agli autori

**Comandi per contributori:**
* status
  * significato: mostra le differenze tra il file di indice e il commit HEAD
  * scopo: serve per tenere traccia dei files modificati, del ramo attuale e di altre informazioni riguardo il cosiddetto index
  * esempio: 
    * ```git status [-s] in un repo con files modificati```
* diff
  * significato: Mostra le modifiche tra commit, commit e working tree
  * scopo: confrontare rapidamente le modifiche tra commit
  * esempi: 
    * ```git diff README (mostra le modifiche nel file rispetto all'ultimo commit)```
    * ```git diff <8digit-commit-hash> README (confrontato al ramo XXXX)```
    * ```git diff HEAD README```
    * ```git diff <8digit-commit-hash> HEAD README (cambiamenti “da” “a”)```

* checkout
  * significato: permette il cambio di contesto dei rami oppure ripristina il working tree
  * scopo: poter passare rapidamente da un ramo all’altro
  * esempio: 
    * ```git checkout -b dev (crea e switcha in ramo dev)```
    * ```git checkout master```
    * ```git checkout README```

* branch
  * significato: 
  * scopo: permette la gestione dei rami 
  * esempio: 
    * ```git branch dev```

* stash
  * significato: sposta le modifiche non ancora salvate in una directory di lavoro temporanea e le riapplica dopo un’azione
  * scopo: serve a salvare il lavoro in un'area temporanea e a rispristinare le modifiche in un secondo momento
  * esempio: 
     * ```git stash save "aggiunto css agli asset”```
     * ``` vi file; git commit -a -m "..."```
     * ```git stash pop```

* rebase
  * significato: è un'azione che consente di riscrivere i commit da un ramo a un altro ramo. In sostanza, Git elimina  i commit da un ramo e li aggiunge a un altro.
  * scopo: tenere la timeline lineare rispetto a quanto accade con git merge
  * esempio: 
    * ```git checkout test; git rebase master```
* reset
  * significato: comando per gestire eventuali errori
  * scopo: ripristinare lo stato coerente da un’azione errate
  * esempio: 
    * ```git reset –hard HEAD~1 (annullare l’ultimo commit)```
* push
  * significato: aggiorna il repository remoto
  * scopo: aggiorna i riferimenti remoti utilizzando i riferimenti locali, inviando gli oggetti necessari per completare i riferimenti forniti.
  * esempio: 
    * ```git push -u origin master```
* merge
  * significato: unisce due o più timeline di sviluppo insieme
  * scopo: incorpora le modifiche dai commit con nome (dal momento in cui le loro timeline si sono discostate dal ramo corrente) nel ramo corrente
  * esempio: 
    * ```git checkout master; git merge dev```
* remote
  * significato: gestisce l'insieme di repository remoti  di cui monitori i branch.
  * scopo: collegare il repository locale con uno o più repository remoti
  * esempio: 
    * ```git remote add origin http://github.com/consiglionazionaledellericerche/cool-jconon```

**Comandi per manutentori (come precedenti)**
* tag
  * significato: contrassegnare punti specifici nella cronologia di un repository come importanti
  * scopo: rendere recuperabile il progetto in uno specifico punto della timeline
  * esempio: 
    * ```git tag -a 1.0.0 -m "prima versione 1.0.0"```

 **conventional commits** https://www.conventionalcommits.org/
* **feat** (nuova funzionalità)
* **fix** (bug fix)
* **docs** (modifiche alla documentazione)
* **style** (formattazione, punti e virgola mancanti, ecc; nessuna modifica del codice)
* **refactor** (refactoring del codice di produzione)
* **test** (aggiunta di test mancanti, test di refactoring; nessuna modifica del codice di produzione)
* **chore** (updating grunt tasks etc; nessuna modifica del codice di produzione

**Link utili**:
* libro di GIT (free PDF, EPUB, MOBI): https://git-scm.com/book/en/v2 
* come correggere alcuni errori comuni in git: https://ohshitgit.com/ 
* gioco basato su browser che spiega il branching: https://learngitbranching.js.org/ 
* git prompt https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh 
* git from the Bottom Up: https://jwiegley.github.io/git-from-the-bottom-up/ 
* Git cheatsheet: http://www.ndpsoftware.com/git-cheatsheet.html 
* Commit are snapshots: https://github.blog/2020-12-17-commits-are-snapshots-not-diffs/
