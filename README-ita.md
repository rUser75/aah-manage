
# aah-manage.py - Script di Gestione per Ansible Automation Hub

## Panoramica

`aah-manage.py` è uno strumento da riga di comando progettato per facilitare la gestione di varie risorse all'interno di Ansible Automation Hub. Questo script consente agli utenti di eseguire operazioni come elencare, sincronizzare e gestire gli Execution Environments (EE) e le collezioni di Ansible. È uno strumento essenziale per gli amministratori che desiderano gestire in modo efficiente le loro istanze di Ansible Automation Hub.

## Caratteristiche

- **Elenco degli Execution Environments**: Recupera e visualizza un elenco degli Execution Environments disponibili.
- **Sincronizzazione dei Repository**: Avvia la sincronizzazione dei repository remoti per garantire che siano aggiornati.
- **Gestione delle Collezioni**: Elenca, rimuove o elimina collezioni di Ansible dai repository o dal sistema.
- **Generazione di Token di Autenticazione**: Crea nuovi token API per l'autenticazione.
- **Elenco delle Risorse Disponibili**: Visualizza tutti i repository e le collezioni disponibili con le loro descrizioni e versioni.

## Prerequisiti

- Python 3.9 o successivo
- Pacchetti Python richiesti: `requests`, `termcolor`, `jq`, `urllib3`

## Installazione

1. **Clona il Repository**: 
   ```bash
   git clone <repository-url>
   cd <repository-directory>


## Installa le Dipendenze:
```sh
pip install requests termcolor jq urllib3
```

Imposta le Variabili d'Ambiente (opzionale):

* AUTH_TOKEN: Il tuo token di autenticazione API.
* AAH_SERVER: L'indirizzo del server per Ansible Automation Hub.

##Utilizzo
### Comandi di Base

* Elenca gli Execution Environments:
```
python aah-manage.py --getEEList
```

* Sincronizza un Repository Remoto:

```
python aah-manage.py --sync <community|rh-certified>
```

* Elenca i Repository e le Collezioni Disponibili:
```
python aah-manage.py --listAvailables
```

* Genera un Nuovo Token di Autenticazione:
```
python aah-manage.py --generateAuthToken <user:password>
```
### Gestione delle Collezioni

* Elenca le Collezioni:
```
python aah-manage.py --getCollectionList --namespace <namespace> --collection <collection_name> --repositoryName <repository_name>
```

*Rimuovi una Collezione dal Repository:
```
python aah-manage.py --removeCollection --namespace <namespace> --collection <collection_name> --repositoryName <repository_name>
```

Elimina una Collezione dal Sistema:
```
python aah-manage.py --deleteCollection --namespace <namespace> --collection <collection_name> --repositoryName <repository_name>
```
### Autenticazione

* Utilizzando Argomento da Riga di Comando:
```
python aah-manage.py --authToken <TOKEN>
```
Utilizzando Variabile d'Ambiente: Assicurati che AUTH_TOKEN sia impostato nel tuo ambiente.

## Opzioni
* --authToken <TOKEN>: Token API per l'autenticazione.
* --generateAuthToken <user:password>: Genera un nuovo token di autenticazione.
* --getEEList: Elenca gli Execution Environments disponibili.
* --getEEVersion: Elenca le versioni degli Execution Environments disponibili.
* --listAvailables: Elenca tutti i repository e le collezioni disponibili.
* --deleteEE <EEname> <SHA>: Elimina l'immagine di Execution Environment specificata.
* --getCollectionList: Elenca le collezioni in un namespace e repository specificato.
* --removeCollection: Rimuovi una collezione specificata da un repository.
* --deleteCollection: Elimina una collezione specificata dal sistema.
* --namespace <namespace>: Specifica il namespace per la gestione delle collezioni.
* --collection <collection_name>: Specifica il nome della collezione per la gestione.
* --repositoryName <repository_name>: Specifica il nome del repository per la gestione.
* --sync <REPOREMOTENAME>: Sincronizza un repository remoto.
* -k: Consenti connessioni server non sicure quando si utilizza SSL.
* -v: Abilita l'output dettagliato per il debug.

## Note
Assicurati che la variabile d'ambiente AAH_SERVER sia impostata sull'indirizzo del server corretto.
Lo script richiede le autorizzazioni appropriate per eseguire operazioni su Ansible Automation Hub.

nello script si fa riferimento a community|rh-certified potrebbe cambiare da installazione ad installazione

## Risoluzione dei Problemi
Errori di Autenticazione: Verifica che il token API sia corretto e non sia scaduto.
Problemi di Connessione: Assicurati che l'indirizzo del server sia raggiungibile e corretto.
Dipendenze Mancanti: Installa i pacchetti Python richiesti utilizzando pip.

