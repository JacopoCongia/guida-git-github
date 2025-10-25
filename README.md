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
