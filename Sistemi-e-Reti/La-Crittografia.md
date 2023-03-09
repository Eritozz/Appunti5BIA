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


---

## Caratteristiche della crittografia asimmetrica
- Non è possibile **decifrare e cifrare** con la stessa chiave
- Cifratura e decifratura si applicano con la stessa coppia di chiavi
- Si deeve sempre cifrare con la chiave pubblica del destinatario
- Il messaggio deve essere certificato (applicare un digest) con la propria chiave privata

---

## Funzioni di Hash
Le funzioni di **HASH** trasformano la un qualsiasi testo a **lunghezza arbitraria** in uno a **lunghezza fissa**, inoltre ad un attacco di forza bruta non è possibile risalire al testo da un valore di *HASH*.<br>
Le funzioni HASH più utilizzate nella firma digitale sono: 
- **SHA-256** (Secure Hash Algorithm a 256 bit) **più forte**
- **MD5** (Message Digest versione 5 a 128 bit) **più debole**

---

## I Principali agoritmi a chiave simmetrica
- **DES** : Data Encryption System, creato nel 1977, aveva una chiave a 56 bit, fu violato nel 1999, adesso è ritenuto insicuro.
- **3DES**: è il *DES* applicato 3 volte: creato nel 1978, usa tre chiavi a 56 bit, è abbastanza sicuro ma è possibile violarlo in determinate situazioni.
- **AES**: Advanced Encryption System, creato nel 2001, utilizza una chiave a 128 bit, rimane tuttora inviolato. Esistono anche diverse varianti: *AES-192*, *AES-256* (ancora più sicure).

Il problema dello scambio della chiave, durante una comunicazione diretta, si risolve con un solo modo: si utilizza la crittografia asimmetrica. <br>
Nella crittogrfia asimmetrica si crea una coppia di chiavi pubbliche/private. Poi i soggetti si scambiano le chiavi pubbliche, custodendo gelosamente quella privata. 

---

## Algoritmi di crittografia asimmetrica e i suoi limiti
- **Diffie-Hellman** (usato nei router per le VPN site-to-site)
- **RSA-256** (usato nei certificati digitali per HTTPS)
- **Crittografia a curve ellittiche** (ECC-256) (usato da Google, scusa se è poco)

### I limiti:

- **Protezione della chiave privata**.
Se questa per caso viene scoperta o condivisa è un guaio. Un piccolo trucco consiste nell'aggiungere l'opzione -des3 durante la creazione della chiave privata. Questo comando la cifrerà con l'algoritmo simmetrico TripleDES, usate una password e sarete mediamente al sicuro.
- **La chiave di cifratura deve essere *sempre* più grande del file cifrato**.
Il problema è facilmente risolvibile, cifrate il vostro grosso file con la cifratura simmetrica e poi usate la cifratura asimmetrica per cifrare la password.



<br><br>
by ***Leonardo Canu*** *5BIA*