# Php
## Le basi
Il php è un linguaggio inetrpretato lato server che permette la generazione dinamica di pagine inertet.<br>
>Ogni file *.html* che contiene anche una sola riga in linguaggio php deve avere l'estenzione *.php*. <br>

Tutto il codice php deve essere posto all'interno del tag speciale <code>\<?php</code> e <code>\?></code>

<code>\<?php</code><br>
&emsp;<code>echo "Hello World!";</code><br>
<code>\?></code> <br>

---

## Le variabili
Il php è un linguaggio non tipizzato, pertanto le variabili possono assumere qualsiasi tipo di valore. <br>
Le variabili sono **sempre** precedute dal simbolo del dollaro e un esempio di inizializzazione di una variabile è: <code>\$var = 1;</code><br>
ma il suo valore può essere anche <code>\$var = true;</code>

---

## Echo
Echo è una direttiva che permette di convertire una stringa in tag e linee html.<br>
<code>echo "\<h1> Title \</h1>";</code><br>
La concatenazione avviene tramite i <code>.</code> invece che con i <code>+</code>.<br>Si possono ovviamente concatenare anche le variabili: <br>
<code>\$var = 'Hello';</code> <br>
<code>echo \$var . "World";</code><br>
Output: <code>Hello World</code>

---

## La sintassi
Per il resto, la sintassi del php è molto simile a quella già studiata negli altri linguaggi di programmazione, l'unica differenza è che vengono utilizzate le <code>-></code> al posto dei <code>.</code> per richiamare le funzioni o gli attributi relativi ad un oggetto.

---

## I metodi GET e POST
L'unico modo per passare dei parametri da una pagina all'altra, in php è quellodi i utilizzare i metodi **GET** e **POST** nei form.<br>
Il metodo GET permette di passare i parametri in chiaro, **nella URL**.<br>
Il metodo POST li passa in maniera criptata, **senza vsualizzarli nella URL**.<br>
I valori passati con i metodi POST e GET vengono inseriti all'interno di un array associativo, con l'indice che coincide con la stringa all'interno del name dell'elemendo nella pagina precedente.<br>

*index.php*<br>
<code>\<form action="ProssimaPagina.php" method="post"></code><br>
&emsp;<code>\<input type="text" name="Nome"></code><br>
<code>\</form></code><br>
*ProssimaPagina.php*<br>
<code>\<?php</code><br>
&emsp;<code>echo $_GET['Nome'];</code> (per il metodo POST l'array sarà <code>\$_POST[]</code>)<br>
<code>?></code><br>

---

## Le SESSION
La sessione, in php, è un metodo per poter salvare un dato per tutta l'esecuzione di un programma, a livello globale, fino a che non viene fatto un reload del sito.<br>
In particolare si tratta di un array associativo.<br>
Per avviare una sessione basterà invocare la funzione <code>session_start()</code> e l'array <code>\$_SESSION</code>.<br>
Se volessi salvare un dato all'interno di un campo della sessione basta fare: <code>\$_SESSION['NomeCheVoglio'] = \$valore;</code><br>
Per concludere una sessione manualmente, senza ricaricare la pagine, bisogna usare la funzione <code>session_destroy()</code>.

---

## La libreria mysqli
La Libreria mysqli è una libreria che permette di effettuare le query ad un database.<br>
Per instaurare la connessione ad un database bisogna creare un oggetto mysql e passagli i parametri per la connessione.<br>
<code>\$connessione = new mysqli(indirizzoIP, nomeutente, password, noedatabase);</code><br>
Per effettuare una query si usa invece <br>
<code>\$richiesta = "SELECT tabella.* FROM tabella";</code><br>
<code>\$risultato = \$connessione->query(\$richiesta);</code><br>
Il metodo <code>query()</code> prende in ingresso una stringa e il risultato della query viene salvato nella variabile <code>\$risultato</code>che risulterà come un array bidimenzionale associativo. Per poter scorrere e visualizzare il suo contnuto si usa il metodo <code>fetch_assoc()</code>: si tratta di un metodo con un iteratore interno che ritorna una riga alla volta, sottoforma di array associativo, con i nomi dei campi uguali a quelli dei campi del database. Una volta arrivato all'ultima riga, il valore di ritorno sarà <code>null</code>. Per questo motivo la maniera più efficace per utilizzare <code>fetch_assoc()</code> è quello di inserirla all'interno di un ciclo <code>while</code> e di mettere ogni riga all'interno di una variabile:<br>
<code>while(\$row = \$risultato->fetch_assoc()) {</code><br>
&emsp;<code>echo \$row['colonna']</code><br>
<code>}</code><br>


<br><br>
by ***Leonardo Canu*** *5B-IA*