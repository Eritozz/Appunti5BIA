# Comandi Docker 
## Comandi
- ` > docker images ` visualizza tutte le immagini salvate sulla macchina
- ` > docker rmi nome:tag ` cancella un' immagine
- ` > docker pull nome:tag ` scaricare un'immagine dal repository di Docker Hub
- ` > docker ps ` visualizza tutti i container in esecuzione
    - ` -a ` visualizza tutti i container, anche quelli usati in passato
<br>
- ` > docker rm nome/id `  viene eliminato un container 
- ` > docker rmi nome:tag ` viene eliminata un' immagine
- ` > docker run nome:tag comando ` avvia un container partendo da un' immagine 
    - ` --rm ` al termine dell'esecuzione, elimina il container 
    - ` --name nome ` scegli il nome del container
    - ` -it ` permette di usare la tastiera all'interno del container
    - ` -d ` avvia il container come demone (in background) 
    - ` -v CartellaLocale:CartellaContainer </code > monta un volume all'interno del container
    - ` -p PortaLocale:PortaContainer ` permette di usare il port forwarding 
    - ` -e valiable=valore ` imposta una variabile d'ambiente all'interno del container
<br>
- ` > docker kill nome/IDcontaier `  conclude l'esecuzione di un container
- ` > docker logs nome/IDcontaier ` visualizza gli ultimi log di un container
    - ` -f ` continua a visualizzarli in tempo reale
<br>
- ` > docker exec nome/IDcontainer comando ` entra in un container già attivo
    - ` -it `  permette di usare la tastiera all'interno del container
<br>
- ` > docker inspect IDcontainer ` visualizza tutte le info di un container, anche l'IP interno
- ` > docker build pathDockerfile ` creo la mia immagine dal Dockerfile
    - ` -t nome ` assegna nome all'immagine
    - ` --no-cache ` in fase di build non utilizza i dati salvati nella chache 
<br>
- ` > docker login ` login nel tuo account dockerhub, così da poter pubblicare le  immagini sul proprio repository
- ` > docker push nomeDatoDalSito:tag ` permette di pubblicare un immagine sul tuo repository
- ` > docker tag nome:tag nuovoNome:tag ` aggiunge un nuovo nome all'immagine
- ` > docker-compose up ` cerca il file "docker-compose.yml" e avvia tutto il suo contenuto
- ` > docker-compose down ` conclude l'esecuzione tutti i pricessi avviati dal docker-compose 

---

## Direttive Dockerfile

- ` FROM immagine:tag `  immagine di partenza

- ` RUN istruzione	` esegue l'istruzione durante la build
    - ` -y ` dice "yes" a tutte le direttive durante le installazioni
<br>
- ` COPY nomeFile pathNelContainer ` copia un file nel container
- ` ENTRYPOINT comando ` esegue il comando appena viene avviato il container

---

## Esempio di docker-compose
File: docker-compose.yml 
` version: "2.2" ` (senza quest'istruzione non funziona niente nelle nuove versioni) 
` services: ` 
&emsp;` mioServizio: ` 
&emsp;&emsp;` image: immagine ` (immagine da usare) 
&emsp;&emsp;` ports:  ` (port forwarding) 
&emsp;&emsp;&emsp;` - 8080:80 ` 
&emsp;&emsp;&emsp;` - 8081:443 ` 
&emsp;&emsp;` volumes: ` 
&emsp;&emsp;&emsp;` - RelativePath:pathNelContainer`  	
&emsp;` altroServizio: ` 
&emsp;&emsp;` build: pathDockerfile `(in alternativa alla direttiva "image") 
&emsp;&emsp;` ports: ` 
&emsp;&emsp;&emsp;` - 3306:3306 ` 
&emsp;&emsp;` volumes: ` 
&emsp;&emsp;&emsp; ` - RelativePath:pathNelContainer `

<br><br>
by Leonardo Canu 5B-IA