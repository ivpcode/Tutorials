# Impostare chiavi SSH per il proprio profilo github

## Generare le chiavi ssh

1. Aprire il terminale
2. Lanciare il comando: 
```zsh
ssh-keygen -t rsa -b 4096 -C "yourname@your.email"
```
3. viene chiesto il file in cui salvare le chiavi ssh, è consigliabile mettere un nome che richiami github: es. github_rsa
4. viene chiesta una password di sblocco delle chiavi, dando invio si può evitare la password ma ciò è sconsigliabile. 
5. al termine della procedura sono generati due files con il nome specificato al passo 3, dei due quello con chiave pubblica ha estensione .pub, l'altro è senza estensione ed è la chiave privata.


## Impostare la chiave pubblica nel proprio profilo github

1. loggarsi in gihub
2. cliccare l'icona in alto a destra (quella del proprio account)
3. selezionare la voce "Settings" (penultima in basso)
4. cliccare sulla voce del menu di sinistra "SSH and GPG keys"
5. cliccare il pulsante verde in alto a destra "New SSH key"
6. immettere il nome della key es. "github_rsa - Nome Workstation"
7. incollare il contenuto del file con la chiave pubblica (nel nostro esempio: github_rsa.pub). Il contenuto è un testo che comincia per ssh-rsa.. e termina con la email immessa)
8. confermare con pulsante "add SSH key" e successivamente immettendo la password del proprio account github.


## Utilizzare le chiavi ssh per pushare su github con SmartGit

1. clonare un repository su cui si ha scrittura con SmartGit, utilizzare la vesrione ssh dell'url del repository 
2. al push delle modifiche SmartGit chiede di immettere le credenziali, impostare "Authentication Type: Private Key" e caricare la chiave privata generata in precedenza (nel nostro esempio: github_rsa)
3. immettere la passphrase selezionata al momento della creazione delle chiavi ssh eseguito in precedenza





