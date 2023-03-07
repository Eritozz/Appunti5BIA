# La Crittografia
## Le parole chiave
Le principali parole che utilizzaremo in questo argomento sono:
- La **cifratura** è il procedimento con il quale cifriamo un messaggio applicando
una funzione matematica che rende il messaggio incomprensibile.
- La **decifratura** è l'operazione inverza della cifratura.
- Un **testo in chiaro** è un elemento che non ha subito cifrature.
- Una **funzione *HASH*** è un algoritmo matematico che da un testo di qualsiasi lunghezza
restituisce sempre un testo di lunghezza fissa.
- Un **digest** è l'output ottenuto da una funzione di hash.
- La **chiave** è un elemento fondamentale utilizzato negli algoritmi di crittografia

---

## I tre caratteri principali
Per garantire una comunicazione riservata si devono soddisfare i seguenti requisiti
- **Segretezza**: il messaggio deve essere incomprensibile a terze parti
- **Integrità**: il messaggio non deve essere alterato durante la trasmissione
- **Autenticità**: il destinatario deve essere sempre sicuro che il messaggio ricevuto sia
stato inviato dal mittente e non da qualcun altro che si è spacciato per il mittente.

---

## Come garantire i tre caratteri
La **segretezza** viene garantita grazie alla **crittografia**. Mentre l'**integrità** e l'**autenticità** vengono garantite con la **firma digitale** e ad un *digest*.
- il **digest** è considesrata l'*impronta digitale* del messaggio
- ogni piccola modifica al messaggio comporta uno stravolgimento del digest
- Non è possibile risalire al messaggio originale dal digest, perché contiene troppe
poche informazioni.

---

## I tipi di crittografia
Esistono due categorie di algoritmi crittografici:
- **crittografia simmetrica** utilizza la stessa chiave sia per la cifratura che per la decifratura
- **crittografia asimmetrica**, ha la caratteristica di avere due chiavi distinte, dette pubblica e privata, legate tra loro matematicamente.

---

## Crittografia simmetrica VS Crittografia asimmetrica


||La crittografia ***Simmetrica*** |La crittografia ***Asimmetrica***|
|---|---|---|
|*PRO*|Usando una chiave sola, le operazioni di cifratura e decifratura sono più veloci |Dalla chiave pubblica non si può risalire alla chiave privata. Possiamo quindi distribuirla in modo sicuro. Inoltre ad ogni chiave pubblica corrisponde una sola privata.|
|*CONTRO*|Forte problema della distribuzione delle chiavi private|Le operazioni di cifratura e decifratura sono molto più lente|


<br><br>
by ***Leonardo Canu*** *5BIA*