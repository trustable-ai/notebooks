# 1 - Setup progetto e architettura base

Crea una nuova applicazione Project Dashboard Task con React + Tailwind CSS.

Configura una struttura pulita con:
- Dashboard principale
- Gestione attività
- Componenti UI riutilizzabili
- Servizi separati per database e API

Prepara l'integrazione con Nuvolaris OpenServerless per eventuali funzioni backend serverless.

Implementa una prima versione funzionante con:
- Layout responsive
- Sidebar o menu di navigazione
- Dashboard vuota pronta per statistiche
- Pagina attività con lista iniziale
- Stato globale minimo necessario

Assicurati che l'applicazione sia avviabile e funzionante prima di aggiungere nuove feature.

---

# 2 - Sistema gestione attività con MongoDB e TodoWrite

Implementa il sistema completo di gestione task.

Ogni attività deve avere:
- Titolo
- Descrizione
- Categoria
- Priorità (bassa, media, alta)
- Data di scadenza
- Stato (da fare, in corso, completata)
- Data creazione

Usa MongoDB per salvare le attività.

Crea API o funzioni serverless tramite Nuvolaris OpenServerless per:
- Creare attività
- Modificare attività
- Eliminare attività
- Recuperare lista attività

Integra TodoWrite per gestire le operazioni sulle attività.

Aggiungi una UI completa con:
- Form creazione/modifica
- Lista task
- Filtri per stato e priorità
- Pulsanti funzionanti per completare ed eliminare

Testa ogni operazione prima di procedere.

---

# 3 - Ricerca veloce e cache con Redis

Aggiungi un sistema di ricerca avanzata delle attività.

Implementa:
- Barra di ricerca globale
- Ricerca per titolo e descrizione
- Filtri combinabili per categoria, priorità e stato
- Aggiornamento risultati in tempo reale

Usa Redis per:
- Memorizzare temporaneamente le ricerche frequenti
- Migliorare la velocità di caricamento delle attività
- Gestire eventuali dati temporanei della dashboard

Mantieni la logica backend separata dal frontend.

Verifica che la ricerca funzioni anche con molte attività.

---

# 4 - Dashboard statistiche e miglioramento UI

Realizza la dashboard principale con statistiche sulle attività.

Mostra:
- Numero totale attività
- Attività completate
- Attività ancora da completare
- Attività in ritardo
- Distribuzione per priorità
- Distribuzione per categoria

Crea componenti grafici semplici e leggibili.

Migliora l'interfaccia usando Tailwind CSS:
- Card statistiche
- Tabelle o liste ordinate
- Badge per stato e priorità
- Design responsive desktop/mobile

Aggiungi caricamenti, stati vuoti ed eventuali messaggi di errore.

---

# 5 - Rifinitura, test e preparazione deploy

Controlla tutta l'applicazione Project Dashboard Task.

Verifica:
- Tutte le pagine sono raggiungibili
- Tutti i pulsanti funzionano
- CRUD attività completo
- Ricerca veloce funzionante
- Statistiche aggiornate automaticamente
- Connessione MongoDB stabile
- Cache Redis corretta
- Funzioni Nuvolaris OpenServerless configurate

Migliora:
- Gestione errori
- Performance
- Pulizia del codice
- Responsive design

Prepara la configurazione finale per il deploy.
