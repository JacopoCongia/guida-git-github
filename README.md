# Guida a Git e GitHub
### Una breve guida su come inizializzare un repository in locale con Git, collegarlo a GitHub e a Visual Studio Code
<br><br>
## **1)** [Scarica e installa Git sul tuo computer](https://git-scm.com/)

<img width="1057" height="533" alt="image" src="https://github.com/user-attachments/assets/c8edd93c-d6e7-4887-9223-1922bb18e550" />

## **2)** [Scarica e installa Visual Studio code sul tuo computer](https://code.visualstudio.com/Download) (Scegli la versione compatibile con il tuo sistema operativo)

<img width="1475" height="771" alt="image" src="https://github.com/user-attachments/assets/35f660ea-146b-4111-b5ee-5a99eb3ef2ea" />

## **3)** [Crea un account su GitHub, se non lo hai già](https://github.com/)

## **4)** Visual Studio Code

Ora dobbiamo creare il primo repository in locale per poi caricarlo su GitHub (che è come un contenitore in cloud dei nostri repository)

Dopo aver lanciato Visual Studio Code
1. Fai click su Terminal
2. Fai click su New Terminal
3. Vedrai il terminale comparire in basso (anche detta shell o CLI)

<img width="1308" height="1143" alt="image" src="https://github.com/user-attachments/assets/083675ea-64ee-41a6-80e4-e6b99c5ef983" />


### Ora seleziona la CLI di Git (Git Bash)
<img width="1008" height="583" alt="image" src="https://github.com/user-attachments/assets/93806882-3074-44cd-84e4-f72227748a18" />

## **5)** Crea il repository locale
1. Usando il terminale su Visual Studio Code naviga nella directory dove vuoi creare la cartella che conterrà il tuo progetto, ad esempio questa è la mia:  
```cd /Users/Jako/progetti-personali/ ```

2. Crea la cartella che conterrà il tuo progetto:  
```mkdir primo-progetto```

3. Naviga dentro alla cartella appena creata (Nota: puoi premere il tasto tab sulla tastiera per "autocompletare" il nome della directory ad esempio "cd prim" + TAB verrà autocompletato con "primo-progetto"):  
```cd primo-progetto```

4. Inizializza il repository locale. Questo comando dice a Git di "tenere sotto controllo" la cartella che hai scelto (Verrà creata una cartella nascosta chiamata ```.git/```:  
```git init```

5. Per controllare che tutto sia andato a buon fine puoi scrivere:  
  ```git status```

Dovresti vedere:  
```
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```  

6. Adesso crea un nuovo file:  
```touch ciaoMondo.c```

7. Aggiungi tutti i file presenti nella cartella al "tracking" di Git (il "." indica tutti i file):  
```git add .``` oppure un singolo file: ```git add ciaoMondo.c```

8. Crea il primo commit (il parametro -m sta per "messaggio" e il parametro successivo è il messaggio stesso):  
```git commit -m "Primo commit"```

## **6)** Crea il repository su GitHub  

Naviga sulla tua pagina di GitHub e crea un nuovo repository e dagli uno nome tipo ```mio-progetto```

<img width="721" height="506" alt="image" src="https://github.com/user-attachments/assets/b1ea5dd5-6f58-4491-aa0b-e8958891419c" />

## **7)** Autenticati con GitHub CLI
Prima di collegare il nostro repository locale a quello remoto dobbiamo autenticarci con il nostro account di GitHub.  
Il modo più semplice è usando GitHub CLI, che possiamo installare direttamente dal terminale di Git Bash.  
1. Assicurati di usare Git Bash su Visual Studio Code (vedi Punto 3 di questa guida)  
2. Installa GitHub CLI da linea di comando (segui le istruzioni a schermo):  
   ```winget install GitHub.cli```
3. Autenticati con il tuo account di GitHub (seleziona "Login with a web browser" e segui la procedura)  
   ```gh auth login```  
4. Ora sei pronto per il passo successivo

## **8)** Collega il repository locale a quello remoto

1. Nel terminale, su Visual Studio Code, scrivi (**sostituisci l'url con quello del tuo progetto**):  
```git remote add origin https://github.com/JacopoCongia/mio-progetto```

Puoi verificare che tutto sia andato a buon fine scrivendo:  
```git remote -v```

2. Ora invia il tuo primo commit online:  
```git push -u origin main```  
o, se il tuo branch locale si chiama ```master```  
```git push -u origin master```

## **9)** Verifica che tutto sia andato a buon fine:

Apri GitHub nel browser e vedrai i file che hai caricato nel tuo repository!

---  

# Comandi Utili (Forniti da ChatGPT)
## 🧩 1️⃣ Configurazione iniziale

| Comando | Descrizione |
|----------|-------------|
| `git config --global user.name "Tuo Nome"` | Imposta il nome che comparirà nei commit |
| `git config --global user.email "tu@email.com"` | Imposta l’email associata ai commit |
| `git config --global -l` | Mostra le configurazioni correnti |
| `git init` | Inizializza un nuovo repository locale |
| `git clone <url>` | Clona un repository esistente da GitHub |

---

## 📂 2️⃣ Aggiungere e controllare i file

| Comando | Descrizione |
|----------|-------------|
| `git status` | Mostra i file modificati, aggiunti o in attesa di commit |
| `git add .` | Aggiunge tutti i file modificati all’area di staging |
| `git add nomefile` | Aggiunge solo un file specifico |
| `git rm --cached nomefile` | Toglie un file dallo staging (ma non lo cancella dal disco) |

---

## 🧾 3️⃣ Creare e gestire i commit

| Comando | Descrizione |
|----------|-------------|
| `git commit -m "Messaggio"` | Crea un nuovo commit con messaggio |
| `git commit -am "Messaggio"` | Aggiunge e committa tutti i file già tracciati in un solo passo |
| `git log` | Mostra la cronologia dei commit |
| `git show` | Mostra i dettagli dell’ultimo commit |
| `git diff` | Mostra le differenze tra file modificati e l’ultimo commit |

---

## 🌿 4️⃣ Lavorare con i branch

| Comando | Descrizione |
|----------|-------------|
| `git branch` | Mostra i branch locali |
| `git branch nome-branch` | Crea un nuovo branch |
| `git checkout nome-branch` | Passa a un branch diverso |
| `git switch nome-branch` | Alternativo moderno a `checkout` |
| `git merge nome-branch` | Unisce un branch nel branch attuale |
| `git branch -d nome-branch` | Elimina un branch locale |

---

## 🌐 5️⃣ Collegare e sincronizzare con GitHub

| Comando | Descrizione |
|----------|-------------|
| `git remote add origin <url>` | Collega il repo locale a GitHub |
| `git remote -v` | Mostra gli URL remoti configurati |
| `git push -u origin main` | Invia il branch “main” su GitHub |
| `git pull` | Riceve e integra le modifiche dal remoto |
| `git fetch` | Scarica aggiornamenti dal remoto senza integrarli subito |

---

## 🧰 6️⃣ Ripristinare e risolvere errori

| Comando | Descrizione |
|----------|-------------|
| `git restore nomefile` | Ripristina un file modificato all’ultimo commit |
| `git reset HEAD nomefile` | Toglie un file dallo staging |
| `git reset --hard` | Riporta tutto all’ultimo commit (**⚠️ distruttivo**) |
| `git revert <hash>` | Crea un nuovo commit che annulla quello indicato |
| `git stash` | Salva modifiche temporaneamente senza committarle |
| `git stash pop` | Recupera le modifiche salvate |

---

## 🧭 7️⃣ Informazioni e diagnostica

| Comando | Descrizione |
|----------|-------------|
| `git status` | Stato attuale del repository |
| `git log --oneline --graph --all` | Mostra cronologia compatta e visuale |
| `git remote show origin` | Mostra info sul remoto |
| `git config --list` | Mostra la configurazione attuale di Git |

