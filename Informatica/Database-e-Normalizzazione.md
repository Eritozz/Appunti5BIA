# I Database
## Le basi
I database nascono come alternativa ai precedenti **record**, a causa della poca flessibilità, dei priblemi di **accesso concorrente** e quindi di coerenza dei dati.<br>

Ogni database ha un sistema di gestione automatico, detto **DBMS** e tutte le operazioni, dette **transazioni** che permermettono di ottenere una **vista**.<br>

Ogni transazione deve:
- essere **atomica** ovvero non visibile dall'esterno e non può essere interrotta
- essere **consistente** ovvero dice che un database deve essere coerente
- essere **isolation** ovvero non si può vedere cosa succede durante una transazione
- essere **durabie** ovvero il suo effetto deve essere permanente
Tutto si racchiude nell'acronimo **ACID**.

Esiste anche un sistema di **rollback**, che permette far di tornare il database al momento prima della transazione.

---

## Lo schema ER (entità e relazione)
Esemprio di database con uno schema ER, con anche le relazioni


---

## Lo schema logico
Esempio del database soprastante con uno schema logico
`Studente: ID, Nome, Cognome, IDClasse;`
`Classe: ID, Anno, Sezione;`

---

## La normalizzazione
Le 3 regole per la normalizzazione:
- **La prima regola**: non utilizzare campi multipli in una singola tabella per memorizzare dati simili.
- **La seconda regola**: tutti i campi di una tabella devono dipendere da tutta la chiave primaria.
- **La terza regola**: tutti i campi di una tabella che non sono relativi dalla chiave non appartengono alla tabella.

<br><br>
by ***Leonardo Canu*** *5B-IA*