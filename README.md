# Caveau — l'interfaccia dell'app

Questo repository contiene **solo il vestito** di Caveau: la pagina, il
foglio di stile, il codice che disegna le schede. È pubblico perché lo è
comunque: qualunque app web consegna al browser il proprio HTML e il proprio
JavaScript, e chi apre gli strumenti da sviluppatore li legge. Nasconderlo
sarebbe una finzione, non una misura di sicurezza.

**Qui dentro non c'è nulla di riservato.**

| Cosa | Dove vive |
|---|---|
| Interfaccia (questo repository) | pubblica, per forza di cose |
| Dati delle cantine | database privato, una riga per proprietario |
| Foto | archivio privato, aperto solo da link firmati che scadono |
| Motore di lettura e riquotazione | funzioni sul server |
| Chiavi dei modelli | segreti del progetto, mai nel browser |
| Elenco degli invitati | database, gestito da chi amministra |

La chiave che compare in `dati.js` è la **chiave pubblicabile**: è fatta per
stare nel browser. Da sola non apre niente — è il database, riga per riga, a
decidere che cosa può vedere chi la usa. Una copia di questo repository è un
guscio vuoto: nessuna cantina, nessuna foto, nessuno storico.

## Struttura

    index.html              la porta: iscrizione (con chi ti presenta), ingresso, password dimenticata
    privacy.html            l'informativa sulla privacy (italiano e inglese)
    app.js                  l'applicazione (italiano)
    dati.js                 l'unico file che parla col database (italiano)
    app.en.js, dati.en.js   gli stessi due file in inglese
    supabase.js             la libreria del database
    sw.js                   il guardiano dell'involucro (installazione e rete lenta)
    manifest.webmanifest    quello che rende l'app installabile
    icona-*.png             il marchio

## Pubblicare una versione nuova

1. Sostituisci i file.
2. Cambia `VERSIONE` in `sw.js` (es. `caveau-19.1`).

Senza il passo 2 chi ha già installato l'app continua a vedere la versione
vecchia: il guardiano serve la copia che ha in cache finché il nome non cambia.

## Soci

Ci si iscrive indicando chi ti presenta; il Desk approva dalla stanza **05 Desk** dell'app. Chi è approvato è socio del club: una cantina privata, lo Speakeasy (la bacheca fra soci) e l'elenco dei soci. Il Desk segna i fondatori con il bottone **Fondatore**. La modalità di iscrizione (`aperta`, `invito` o `presentazione`) e la quota stanno nella tabella `configurazione`.
