# Comandi Docker 
## Comandi
- <code> > docker images </code>
visualizza tutte le immagini salvate sulla macchina

- <code> > docker rmi *nome:tag* </code>
cancella un' immagine

- <code> > docker pull *nome:tag* </code>
scaricare un'immagine dal repository di Docker Hub

- <code> > docker ps </code>
visualizza tutti i container in esecuzione
    - <code> -a </code> visualizza tutti i container, anche quelli usati in passato

- <code> > docker rm *nome/id* </code> 
viene eliminato un container 

- <code> > docker rmi *nome:tag* </code>
viene eliminata un' immagine

- <code> > docker run *nome:tag comando* </code>
avvia un container partendo da un' immagine 
    - <code> --rm </code> al termine dell'esecuzione, elimina il container 
    - <code> --name *nome* </code> scegli il nome del container
    - <code> -it </code> permette di usare la tastiera all'interno del container
    - <code> -d </code> avvia il container come demone (in background) 
    - <code> -v *CartellaLocale:CartellaContainer* </code > monta un volume all'interno del container
    - <code> -p *PortaLocale:PortaContainer* </code> permette di usare il port forwarding 
    - <code> -e *valiable=valore* </code> imposta una variabile d'ambiente all'interno del container

- <code> > docker kill *nome/IDcontaier* </code>
 conclude l'esecuzione di un container

- <code> > docker logs *nome/IDcontaier* </code>
visualizza gli ultimi log di un container
    - <code> -f </code> continua a visualizzarli in tempo reale

- <code> > docker exec *nome/IDcontainer comando* </code>
entra in un container già attivo
    - <code> -it </code>  permette di usare la tastiera all'interno del container

- <code> > docker inspect *IDcontainer* </code>
visualizza tutte le info di un container, ance l'IP interno

- <code> > docker build *pathDockerfile* </code>
creo la mia immagine dal Dockerfile
    - <code> -t nome </code> assegna nome all'immagine
    - <code> --no-cache </code> in fase di build non utilizza i dati salvati nella chache 

- <code> > docker login </code>
login nel tuo account dockerhub, così da poter pubblicare le  immagini sul proprio repository

- <code> > docker push *nomeDatoDalSito:tag* </code>
permette di pubblicare un immagine sul tuo repository

- <code> > docker tag *nome:tag nuovoNome:tag* </code>
aggiunge un nuovo nome all'immagine

- <code> > docker-compose up </code>
cerca il file "**docker-compose.yml**" e avvia tutto il suo contenuto

- <code> > docker-compose down </code>
conclude l'esecuzione tutti i pricessi avviati dal docker-compose 

---

## Direttive Dockerfile

- <code> FROM *immagine:tag* </code>  immagine di partenza

- <code> RUN *istruzione*	</code> esegue l'istruzione durante la build
    - <code> -y </code> dice "yes" a tutte le direttive durante le installazioni

- <code> COPY *nomeFile* *pathNelContainer* </code> copia un file nel container
- <code> ENTRYPOINT *comando* </code> esegue il comando appena viene avviato il container

---

## Esempio di docker-compose
File: ***docker-compose.yml*** <br>
<code> version: "2.2" </code> (senza quest'istruzione non funziona niente nelle nuove versioni) <br>
<code> services: </code> <br>
|&emsp; <code> mioServizio: </code> <br>
|&emsp;|&emsp; <code> image: *immagine* </code> (immagine da usare) <br>
|&emsp;|&emsp; <code> ports:  </code> (port forwarding) <br>
|&emsp;|&emsp;|&emsp; <code> - *8080:80* </code> <br>
|&emsp;|&emsp;|&emsp; <code> - *8081:443* </code> <br>
|&emsp;|&emsp; <code> volumes: </code> <br>
|&emsp;|&emsp;|&emsp; <code> - *RelativePath:pathNelContainer*  </code > <br>      	
|&emsp; <code> altroServizio: </code> <br>
|&emsp;|&emsp; <code> build: pathDockerfile </code>(in alternativa alla direttiva "image") <br>
|&emsp;|&emsp; <code> ports: </code> <br>
|&emsp;|&emsp;|&emsp; <code> - *3306:3306* </code> <br>
|&emsp;|&emsp;	 <code> volumes: </code> <br>
|&emsp;|&emsp;|&emsp; <code> - *RelativePath:pathNelContainer* </code><br>

<br><br>
by ***Leonardo Canu***
*5B-IA*