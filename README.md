DAY 1

DESCRIZIONE
Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare il layout come da screenshot allegato.
Al caricamento della pagina, effettuate una chiama ajax all'API di Yu Gi Oh: https://db.ygoprodeck.com/api/v7/cardinfo.php
e con i dati restituiti, stampate una card per ogni carta.
**Bonus:**
Creare un componente loader da visualizzare fintantoché i risultati non sono pronti.

DESCRIZIONE
Continuate a lavorare nella stessa repo di ieri e aggiungete una select per filtrare i risultati in base all’archetipo.
Quando l'utente seleziona un valore dalla lista, viene effettuata una chiamata alle API con l'archetipo selezionato (usare solo $emit no store)

BONUS
Popolare dinamicamente le option della select chiamando questo endpoint dell'api: https://db.ygoprodeck.com/api/v7/archetypes.php
Creare un componente che mostri il numero totale di risultati ottenuti.
Usare Promise all solo su created (vedi documentazione axios su github) per fare in modo che i dati delle due api siano disponibili contemporaneamente.