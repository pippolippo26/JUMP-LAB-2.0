JUMP LAB 2.0 – PWA iPhone

CONTENUTO
- index.html: app blu aggiornata, camera frontale, pose tracking, test, anteprima live, salvataggio/scarto, archivio con filtri/statistiche/grafico e impostazioni profilo.
- manifest.json: configurazione PWA.
- sw.js: cache base.
- icon-192.png / icon-512.png: icona JUMP LAB ricavata dal pittogramma fornito, con palette blu.

PUBBLICAZIONE
1. Crea un repository GitHub.
2. Carica TUTTI i file nella radice del repository.
3. Settings > Pages > Deploy from a branch > main > /(root) > Save.
4. Apri l'indirizzo HTTPS con Safari su iPhone.
5. Condividi > Aggiungi alla schermata Home.

FLUSSO TEST
1. Nella schermata Impostazioni inserisci altezza (e peso) e premi Salva: i dati restano memorizzati e puoi modificarli quando vuoi.
2. In Misurazione attiva la fotocamera e inquadra tutto il corpo, inclusi piedi e pavimento.
3. Resta fermo circa un secondo: la calibrazione avviene in automatico (pulsante Ricalibra se sposti il telefono).
4. Premi Inizia test. Il video mostra la posa tracciata.
5. Durante il salto compare una preview live dell'altezza massima stimata.
6. Dopo l'atterraggio compare il risultato; premi Fine test.
7. Scegli Salva nello storico o Scarta salto.
8. Premi nuovamente Inizia test per ripartire da zero.

METRICHE
- Altezza: elevazione stimata della punta del piede in cm.
- Tempo di volo: secondi.
- Velocità media di salita: altezza massima / tempo tra stacco e picco, in m/s.
- Stima da tempo di volo: h = g*T^2/8, conservata come confronto nello storico.

LIMITI
La calibrazione da statura è una scala prospettica semplificata. La camera monoculare non misura direttamente la profondità e le coordinate dei piedi possono oscillare. La velocità riportata è media, non velocità istantanea al picco. Per misure scientifiche serve validazione contro pedana o sistema ottico. Il modello MediaPipe è caricato da CDN: al primo avvio serve internet. Il prototipo non è un dispositivo medico o certificato.


CORREZIONE FOTOCAMERA (BUILD CAMERA FIX)
La richiesta del permesso fotocamera ora avviene immediatamente al tocco di “Attiva fotocamera”, prima del download del modello AI. Il caricamento MediaPipe è dinamico e ha fallback GPU -> CPU. Per usare la fotocamera è necessario aprire il sito pubblicato in HTTPS (GitHub Pages) da Safari e concedere il permesso. Dopo aver aggiornato GitHub Pages, chiudi e riapri la PWA; se persiste una vecchia versione, apri il sito in Safari e ricaricalo.


AGGIORNAMENTO v2.1
- Calibrazione automatica appena il corpo è inquadrato per intero e fermo.
- Altezza e dati atleta solo in Impostazioni, salvati in memoria locale.
- Rimosso l'angolo del ginocchio.
- Velocità in m/s (i salti già salvati vengono convertiti automaticamente).

AGGIORNAMENTO v2.2
- Banner di calibrazione grande dentro l'inquadratura (barra di avanzamento, poi "CALIBRAZIONE COMPLETATA" in verde).
- Bordo dell'inquadratura verde a calibrazione completata.
- Dopo "Fine test" compare sempre il popup: Salva/Scarta se il salto è valido, altrimenti "Riprova".


AGGIORNAMENTO v2.3
- Storico: i punti del grafico ora sono collegati da una linea.
