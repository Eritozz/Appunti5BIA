# NAT
## Caratteristiche di NAT

Poichè le reti sono comunemente implementati con indirizzi IPv4 privati, per consentire ad un dispositivo di accedere a risorse fuori dalla propria LAN si utilizza il NAT, che **traduce gli indirizzi privati in indirizzi pubblici**.<br>

> Il NAT consiste nel tradurre tutti gli indirizzi privati di una rete un uno pubblico.

Tutto ciò viene effettutato con una tabella di mapping degli indirizzi.<br>

Terminologia:
- **Indirizzo Interno**: L'indirizzo del dispositivo che viene tradotto da NAT.
- **Indirizzo Esterno**: Indirizzo del dispositivo di destinazione.
- **Indirizzo Locale**: Un indirizzo locale è qualsiasi indirizzo visualizzato nella parte interna della rete.
- **Indririzzo Globale**: Un indirizzo globale è qualsiasi indirizzo visualizzato nella
parte esterna della rete.

## Tipi di NAT
esistono 2 tipi di NAT:

### Il NAT statico
Il NAT statico utilizza un mapping uno-a-uno degli indirizzi locali e globali, vengono *impostati dall'amministratore* e **rimangono costanti**. <br>
Viene usato per i server WEB o servizi che devono disporre un indirizzo accessibile da Internetin qualsiasi momento. <br> 

### Il NAT dinamico
Il NAT dinamico utilizza *un pool di indirizzi pubblici e li assegna dinamicamente* in **base all'ordine di arrivo**. <br>

### Il Port Address Translation (PAT)
Il PAT, noto come NAT overload **mappa più indirizzi IPV4 privati su un singolo indirizzo IPv4 pubblico**. <br>
Il PAT si assicura che i dispositivi utilizzino un numero di porta TCP diverso per ogni sessione con un server su Internet. <br>
PAT tenta di preservare la porta di origine originale. Se la porta di origine originale è già utilizzata, PAT assegna il primo numero di porta disponibile a partire dall'inizio del gruppo di porte appropriato 0-511, 512-1,023 o 1.024-65.535. <br>
Quando non sono disponibili più porte e sono presenti più indirizzi esterni nel pool di indirizzi, PAT passa all'indirizzo successivo per tentare di allocare la porta di origine originale. <br>
Il processo continua fino a quando non ci sono più porte disponibili o indirizzi IPv4 esterni nel pool di indirizzi.

### Confronto tra NAT e PAT
In sintesi NAT mappa soltanto gli indirizzi, il PAT mappa anche la porta.

## Vantaggi e svantaggi di NAT
### Vantaggi
Vantaggi del NAT:
- NAT conserva lo schema di indirizzamento legalmente registrato consentendo la privatizzazione delle intranet.
- NAT conserva gli indirizzi tramite il multiplexing a livello di porta dell'applicazione.
- NAT aumenta la flessibilità delle connessioni alla rete pubblica.
- NAT fornisce coerenza per gli schemi di indirizzamento della rete interna.
- NAT consente allo schema di indirizzi IPv4 privato esistente di rimanere pur consentendo un facile passaggio a un nuovo schema di indirizzamento pubblico.
- NAT nasconde gli indirizzi IPv4 degli utenti e di altri dispositivi.

### Svantaggi
Sventaggi nell'utilizzo del NAT:
- NAT aumenta i ritardi di inoltro.
- L'indirizzamento end-to-end è perduto.
- La tracciabilità IPv4 end-to-end viene persa.
- NAT complica l'uso di protocolli di tunneling, come IPsec.
- I servizi che richiedono l'avvio di connessioni TCP dalla rete esterna o protocolli stateless, ad esempio quelli che utilizzano UDP, possono essere interrotti.

<br><br>
by ***Leonardo Canu*** *5B-IA*