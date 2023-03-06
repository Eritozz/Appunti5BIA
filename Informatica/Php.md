# Php
## Le basi
Il php è un linguaggio inetrpretato lato server che permette la generazione dinamica di pagine inertet.
>Ogni file *.html* che contiene anche una sola riga in linguaggio php deve avere l'estenzione *.php*. 

Tutto il codice php deve essere posto all'interno del tag speciale `<?php` e `?>`

`<?php`<br>
&emsp;`echo "Hello World!";`<br>
`?>` <br>

---

## Le variabili
Il php è un linguaggio non tipizzato, pertanto le variabili possono assumere qualsiasi tipo di valore. 
Le variabili sono **sempre** precedute dal simbolo del dollaro e un esempio di inizializzazione di una variabile è: `$var = 1;`
ma il suo valore può essere anche `$var = true;`

---

## Echo
Echo è una direttiva che permette di convertire una stringa in tag e linee html.<br>
`echo "<h1> Title </h1>";`<br>
La concatenazione avviene tramite i `.` invece che con i `+`.Si possono ovviamente concatenare anche le variabili: <br>
`$var = 'Hello';` <br>
`echo $var . "World";`<br>
Output: `Hello World`<br>

---

## La sintassi
Per il resto, la sintassi del php è molto simile a quella già studiata negli altri linguaggi di programmazione, l'unica differenza è che vengono utilizzate le `->` al posto dei `.` per richiamare le funzioni o gli attributi relativi ad un oggetto.

---

## I metodi GET e POST
L'unico modo per passare dei parametri da una pagina all'altra, in php è quellodi i utilizzare i metodi **GET** e **POST** nei form.<br>Il metodo GET permette di passare i parametri in chiaro, **nella URL**.<br>Il metodo POST li passa in maniera criptata, **senza vsualizzarli nella URL**.<br>I valori passati con i metodi POST e GET vengono inseriti all'interno di un array associativo, con l'indice che coincide con la stringa all'interno del name dell'elemendo nella pagina precedente.<br>

*index.php*
`<form action="ProssimaPagina.php" method="post">`<br>
&emsp;`<input type="text" name="Nome">`<br>
`</form>`<br>
*ProssimaPagina.php*<br>
`<?php`<br>
&emsp;`echo $_GET['Nome'];` (per il metodo POST l'array sarà `$_POST[]`)<br>
`?>`<br>

---

## Le SESSION
La sessione, in php, è un metodo per poter salvare un dato per tutta l'esecuzione di un programma, a livello globale, fino a che non viene fatto un reload del sito.
In particolare si tratta di un array associativo.
Per avviare una sessione basterà invocare la funzione `session_start()` e l'array `$_SESSION`.
Se volessi salvare un dato all'interno di un campo della sessione basta fare: `$_SESSION['NomeCheVoglio'] = $valore;`
Per concludere una sessione manualmente, senza ricaricare la pagine, bisogna usare la funzione `session_destroy()`.

---

## La libreria mysqli
La Libreria mysqli è una libreria che permette di effettuare le query ad un database.
Per instaurare la connessione ad un database bisogna creare un oggetto mysql e passagli i parametri per la connessione.
`$connessione = new mysqli(indirizzoIP, nomeutente, password, noedatabase);`
Per effettuare una query si usa invece 
`$richiesta = "SELECT tabella.* FROM tabella";`
`$risultato = $connessione->query($richiesta);`
Il metodo `query()` prende in ingresso una stringa e il risultato della query viene salvato nella variabile `$risultato`che risulterà come un array bidimenzionale associativo.<br>
 Per poter scorrere e visualizzare il suo contnuto si usa il metodo `fetch_assoc()`: si tratta di un metodo con un iteratore interno che ritorna una riga alla volta, sottoforma di array associativo, con i nomi dei campi uguali a quelli dei campi del database. Una volta arrivato all'ultima riga, il valore di ritorno sarà `null`. Per questo motivo la maniera più efficace per utilizzare `fetch_assoc()` è quello di inserirla all'interno di un ciclo `while` e di mettere ogni riga all'interno di una variabile:<br>
`while($row = $risultato->fetch_assoc()) {`<br>
&emsp;`echo $row['colonna']`<br>
`}`


<br><br>
by ***Leonardo Canu*** *5B-IA*

&emsp;