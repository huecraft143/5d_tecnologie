# Introduzione allo sviluppo full-stack

Quando parliamo di sviluppo full-stack, ci riferiamo allo sviluppo di tutte le parti di un sito web o di un'applicazione. Lo stack completo inizia con il database e il server web nel back-end, contiene la logica e il controllo dell'applicazione nel mezzo e arriva fino all'interfaccia utente nel front-end.

Il MEAN stack è uno stack puro di JavaScript composto da quattro principali tecnologie, con un insieme di tecnologie di supporto:

- **MongoDB** — il database
- **Express** — il framework web
- **Angular** — il framework front-end
- **Node.js** — il server web

## Breve storia dello sviluppo web

Con l'espansione dell'uso di Internet, le aziende hanno iniziato a prestare maggiore attenzione a come la loro presenza online li rappresentasse. In combinazione con un maggiore supporto dei browser per Cascading Style Sheets (CSS) e JavaScript, questo interesse ha portato a implementazioni front-end più complesse. Non era più sufficiente concatenare HTML; era necessario dedicare tempo a CSS e JavaScript, assicurandosi che apparisse correttamente e funzionasse come previsto. E tutto questo doveva funzionare su browser diversi, molto meno conformi di quanto non siano oggi.

È qui che è emersa la distinzione tra sviluppatore front-end e sviluppatore back-end. La Figura 1.1 illustra questa separazione nel tempo. Mentre i back-end developers si concentravano sulla meccanica dietro le quinte, i front-end developers si concentravano sulla creazione di una buona esperienza utente. Col passare del tempo, sono state poste aspettative più elevate su entrambe le parti, incoraggiando questo trend a continuare. Spesso i developer dovevano scegliere un'area di specializzazione e concentrarsi su di essa.

![[Screenshot 2023-11-15 at 16.18.54.png]]
---
## L'aiuto delle librerie e dei framework agli sviluppatori

Durante gli anni 2000, le librerie e i framework hanno iniziato a diventare popolari e diffusi per i linguaggi più comuni sia nel front-end che nel back-end.

Questi framework sono stati progettati per semplificare la vita degli sviluppatori, abbassando le barriere all'ingresso. Una buona libreria o framework astrae alcune delle complessità dello sviluppo, consentendoti di scrivere codice più velocemente e richiedendo meno competenze approfondite. Questo trend verso la semplificazione ha portato a una rinascita degli sviluppatori full-stack che costruiscono sia il front-end che la logica dell'applicazione dietro di esso, come mostra la Figura 1.2.

La Figura 1.2 illustra una tendenza piuttosto che proclama un definitivo "tutti gli sviluppatori web dovrebbero essere sviluppatori full-stack". Ci sono stati sviluppatori full-stack per tutta la storia del web e in futuro è probabile che alcuni sviluppatori sceglieranno di specializzarsi nello sviluppo front-end o back-end. L'intenzione è mostrare che grazie all'uso di framework e strumenti moderni, non è più necessario scegliere tra un'estremità e l'altra per essere un buon sviluppatore web.

Un enorme vantaggio nell'abbracciare l'approccio dei framework è che puoi essere incredibilmente produttivo, perché avrai una visione completa dell'applicazione e di come si legano le varie parti. 

Pensa a questo come codificare il back-end nel front-end. Alcuni dei framework JavaScript più popolari che lo fanno sono Angular, React e Vue.js.

Accoppiando strettamente il codice dell'applicazione al front-end in questo modo, tende a confondere i confini tra i tradizionali sviluppatori front-end e back-end. Uno dei motivi per cui le persone amano usare questo approccio è che riduce il carico sui server, riducendo così i costi. In sostanza, stai distribuendo il carico computazionale richiesto dall'applicazione spingendo quel carico nei browser degli utenti.

![[Screenshot 2023-11-15 at 16.22.17.png]]
  
## Perché specificamente lo stack MEAN?

Lo stack MEAN unisce alcune delle moderne tecnologie web "best-of-breed" in uno stack potente e flessibile. Una grande caratteristica dello stack MEAN è che non solo utilizza JavaScript nel browser, ma lo utilizza anche ovunque. Utilizzando lo stack MEAN, puoi scrivere il front-end e il back-end nello stesso linguaggio. Detto questo, è più comune costruire la parte Angular dello stack in TypeScript (un superset di JavaScript).

La Figura 1.3 illustra le principali tecnologie dello stack MEAN e mostra dove ciascuna è comunemente utilizzata.
![[Screenshot 2023-11-15 at 16.23.01.png]]
## Introduzione a Node.js: Il server/web platform

Node.js è la N in MEAN. Essere l'ultima lettera non significa che sia meno importante: è il fondamento dello stack! In poche parole, Node.js è una piattaforma software che ti consente di creare il tuo web server e costruire applicazioni web su di esso. Node.js non è di per sé un server web; né è un linguaggio. Contiene una libreria integrata per il server HTTP, il che significa che non è necessario eseguire un programma server web separato come NGINX, Apache o Internet Information Services (IIS). Questo ti offre un maggiore controllo su come funziona il tuo server web, ma aumenta anche la complessità per avviarlo e farlo funzionare, soprattutto in un ambiente live. Con PHP, ad esempio, puoi facilmente trovare un host web condiviso che esegue Apache e inviare alcuni file via FTP e, se tutto va bene, il tuo sito è in esecuzione. Questo funziona perché l'host web ha già configurato Apache per te e altri utenti. Con Node.js, non è così, perché configuri il server Node.js quando crei la tua applicazione. Molti degli host web tradizionali sono indietro nel supporto a Node.js, ma stanno emergendo diversi nuovi host Platform as a Service (PaaS) per affrontare questa esigenza, tra cui Heroku, Nodejitsu e DigitalOcean. L'approccio per distribuire siti live su questi host PaaS è diverso dal vecchio modello FTP, ma è facile quando ci si abitua. Durante la lettura del libro, distribuirai un sito live su Heroku. Un approccio alternativo per l'hosting di un'applicazione Node.js è farlo da soli su un server dedicato o un server virtuale da un provider cloud come AWS o Azure, su cui puoi installare tutto ciò di cui hai bisogno. Veloce, efficiente e scalabile.

![[Screenshot 2023-11-15 at 16.27.36.png]]
## Multithread server classico
Un altro motivo della popolarità di Node.js è che, se programmato correttamente, è estremamente veloce e fa un uso efficiente delle risorse di sistema. Queste caratteristiche consentono a un'applicazione Node.js di servire più utenti con meno risorse del server rispetto alla maggior parte delle altre tecnologie server mainstream. Anche i proprietari di aziende apprezzano l'idea di Node.js perché può ridurre i costi operativi, anche su larga scala.

Come fa Node.js a ottenere ciò? Node.js è leggero sulle risorse di sistema perché è single-threaded, mentre i server web tradizionali sono multithreaded. Nelle sezioni successive, esamineremo cosa significano questi termini, partendo dall'approccio tradizionale multithreaded.

**SERVER WEB TRADIZIONALE MULTITHREADED**

La maggior parte dei server web mainstream attuali sono multithreaded, inclusi Apache e IIS. Questo significa che ogni nuovo visitatore (o sessione) ottiene un thread separato e una quantità associata di RAM, spesso intorno agli 8 MB.

Per fare un'analogia del mondo reale, immagina due persone che entrano in una banca per fare cose diverse. In un modello multithreaded, ognuno andrebbe da un diverso impiegato bancario che gestirebbe le loro richieste, come mostrato nella Figura 1.4.

Puoi vedere nella Figura 1.4 che Simon va all'impiegato bancario 1, e Sally va all'impiegato bancario 2. Nessuna delle due parti è consapevole o influenzata dall'altra. L'impiegato bancario 1 si occupa di Simon, e di nessun altro, per l'intera transazione; lo stesso vale per l'impiegato bancario 2 e Sally.

Questo approccio funziona perfettamente fintanto che hai abbastanza impiegati per servire i clienti. Quando la banca diventa affollata e i clienti superano in numero gli impiegati, il servizio inizia a rallentare e i clienti devono aspettare per essere serviti. Anche se le banche non si preoccupano troppo di questa situazione e sembrano felici di farti stare in fila, lo stesso non vale per i siti web. Se un sito web risponde lentamente, è probabile che gli utenti se ne vadano e non tornino più.

Questa è una delle ragioni per cui i server web sono spesso sovradimensionati e hanno così tanta RAM, anche se non ne hanno bisogno il 90% del tempo. L'hardware è configurato in modo da essere pronto per un enorme picco di traffico. Questa configurazione è simile a quando una banca assume 50 impiegati a tempo pieno e si trasferisce in un edificio più grande perché diventa affollata all'ora di pranzo.

Sicuramente c'è un modo migliore, un modo un po' più scalabile. Ecco dove entra in gioco l'approccio single-threaded.

Nell'approccio single-threaded mostrato nella Figura 1.5, Sally e Simon consegnano le loro richieste allo stesso impiegato bancario. Ma invece di gestire esclusivamente una di esse prima dell'altra, l'impiegato bancario prende la prima richiesta e la passa alla persona migliore per gestirla prima di prendere la richiesta successiva e fare la stessa cosa. Quando l'impiegato bancario viene informato che un compito richiesto è completato, restituisce il risultato al visitatore che ha fatto la richiesta.

Nonostante ci sia un solo impiegato bancario, nessuno dei due visitatori è consapevole dell'altro, e nessuno è influenzato dalle richieste dell'altro. Questo approccio significa che la banca non ha bisogno di diversi impiegati sempre a disposizione. Questo modello non è infinitamente scalabile, naturalmente, ma è più efficiente. Puoi fare di più con meno risorse. Tuttavia, non significa che non dovrai mai aggiungere ulteriori risorse.

Questo particolare approccio è possibile in Node.js grazie alle capacità asincrone di JavaScript, come vedrai.

![[Screenshot 2023-11-15 at 16.29.03.png]]
![[Screenshot 2023-11-15 at 16.29.15.png]]
## Traditional Web Server Request VS node js event loop
![[Screenshot 2023-11-15 at 16.30.54.png]]
![[Screenshot 2023-11-15 at 16.31.55.png]]
## Come fa NodeJS a lavorare su un solo thread?
![[Screenshot 2023-11-15 at 16.32.17.png]]

# Differenza tra CLASSICO e MEAN
**MEAN Stack:**

1. **MongoDB (Database):**
   Nel MEAN stack, useremo MongoDB come database per memorizzare i dati del team di calcio. MongoDB è un database NoSQL che utilizza documenti JSON-like per memorizzare i dati.

2. **Express.js (Back-end):**
   Utilizzeremo Express.js per creare un server e fornire un'API per accedere ai dati del team.

3. **Angular (Front-end):**
   Angular verrà utilizzato per effettuare richieste HTTP all'API e visualizzare i dati sul front-end.

Ecco come potrebbe apparire la configurazione MEAN stack:

**Back-end (Node.js/Express):**
```javascript
const express = require('express');
const app = express();
const teamData = require('./data'); // Dati di esempio del team

// API per restituire i dati del team
app.get('/api/team', (req, res) => {
  // Simuliamo l'accesso a MongoDB, ma usiamo teamData come esempio
  res.json(teamData);
});

// Avvio del server
const PORT = 3000;
app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

**Front-end (Angular):**
```typescript
import { HttpClient } from '@angular/common/http';
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root'
})
export class TeamService {
  private apiUrl = '/api/team'; // L'URL della tua API

  constructor(private http: HttpClient) { }

  getTeamData() {
    return this.http.get(this.apiUrl);
  }
}
```

**Metodo Classico (SQL con PHP e FTP):**

1. **MySQL (Database):**
   Utilizzeremo MySQL come database relazionale per memorizzare i dati del team di calcio.

2. **PHP (Back-end):**
   Utilizzeremo PHP per connetterci al database MySQL, eseguire query e fornire i dati al front-end.

3. **FTP (File Transfer Protocol):**
   Utilizzeremo FTP per trasferire i file PHP sul server.

Esempio di accesso a un database SQL usando PHP:

```php
<?php
$servername = "nome_server";
$username = "nome_utente";
$password = "password";
$dbname = "nome_database";

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
  die("Connessione fallita: " . $conn->connect_error);
}

$sql = "SELECT * FROM squadra";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
  while($row = $result->fetch_assoc()) {
    echo "Nome: " . $row["nome"] . " - Posizione: " . $row["posizione"] . "<br>";
  }
} else {
  echo "0 risultati";
}

$conn->close();
?>
```

In questo approccio classico, utilizziamo PHP per accedere e recuperare i dati da un database MySQL e generare la risposta HTML direttamente dal back-end PHP.

La principale differenza tra i due approcci è che il MEAN stack utilizza tecnologie moderne come MongoDB, Node.js/Express per il back-end e Angular per il front-end, mentre l'approccio classico fa uso di tecnologie tradizionali come PHP, MySQL e FTP per la gestione dei dati e del server.