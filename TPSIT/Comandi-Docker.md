# Comandi Docker 
## Comandi
- ` > docker images `
visualizza tutte le immagini salvate sulla macchina

- ` > docker rmi *nome:tag* `
cancella un' immagine

- ` > docker pull *nome:tag* `
scaricare un'immagine dal repository di Docker Hub

- ` > docker ps `
visualizza tutti i container in esecuzione
    - ` -a ` visualizza tutti i container, anche quelli usati in passato

- ` > docker rm *nome/id* ` 
viene eliminato un container 

- ` > docker rmi *nome:tag* `
viene eliminata un' immagine

- ` > docker run *nome:tag comando* `
avvia un container partendo da un' immagine 
    - ` --rm ` al termine dell'esecuzione, elimina il container 
    - ` --name *nome* ` scegli il nome del container
    - ` -it ` permette di usare la tastiera all'interno del container
    - ` -d ` avvia il container come demone (in background) 
    - ` -v *CartellaLocale:CartellaContainer* </code > monta un volume all'interno del container
    - ` -p *PortaLocale:PortaContainer* ` permette di usare il port forwarding 
    - ` -e *valiable=valore* ` imposta una variabile d'ambiente all'interno del container

- ` > docker kill *nome/IDcontaier* `
 conclude l'esecuzione di un container

- ` > docker logs *nome/IDcontaier* `
visualizza gli ultimi log di un container
    - ` -f ` continua a visualizzarli in tempo reale

- ` > docker exec *nome/IDcontainer comando* `
entra in un container già attivo
    - ` -it `  permette di usare la tastiera all'interno del container

- ` > docker inspect *IDcontainer* `
visualizza tutte le info di un container, ance l'IP interno

- ` > docker build *pathDockerfile* `
creo la mia immagine dal Dockerfile
    - ` -t nome ` assegna nome all'immagine
    - ` --no-cache ` in fase di build non utilizza i dati salvati nella chache 

- ` > docker login `
login nel tuo account dockerhub, così da poter pubblicare le  immagini sul proprio repository

- ` > docker push *nomeDatoDalSito:tag* `
permette di pubblicare un immagine sul tuo repository

- ` > docker tag *nome:tag nuovoNome:tag* `
aggiunge un nuovo nome all'immagine

- ` > docker-compose up `
cerca il file "**docker-compose.yml**" e avvia tutto il suo contenuto

- ` > docker-compose down `
conclude l'esecuzione tutti i pricessi avviati dal docker-compose 

---

## Direttive Dockerfile

- ` FROM *immagine:tag* `  immagine di partenza

- ` RUN *istruzione*	` esegue l'istruzione durante la build
    - ` -y ` dice "yes" a tutte le direttive durante le installazioni

- ` COPY *nomeFile* *pathNelContainer* ` copia un file nel container
- ` ENTRYPOINT *comando* ` esegue il comando appena viene avviato il container

---

## Esempio di docker-compose
File: ***docker-compose.yml*** 
` version: "2.2" ` (senza quest'istruzione non funziona niente nelle nuove versioni) 
` services: ` 
     ` mioServizio: ` 
         ` image: *immagine* ` (immagine da usare) 
         ` ports:  ` (port forwarding) 
             ` - *8080:80* ` 
             ` - *8081:443* ` 
         ` volumes: ` 
             ` - *RelativePath:pathNelContainer*  </code >       	
     ` altroServizio: ` 
         ` build: pathDockerfile `(in alternativa alla direttiva "image") 
         ` ports: ` 
             ` - *3306:3306* ` 
        	 ` volumes: ` 
             ` - *RelativePath:pathNelContainer* `


by ***Leonardo Canu*** *5B-IA*