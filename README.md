# Chi fa cosa

Tracker per segnare ogni giorno chi fa quale compito in casa e con la bambina, con il bilancio della settimana tra le due persone.

La pagina è pubblicata con GitHub Pages. Il codice non contiene dati personali: nomi e compiti segnati sono salvati in un **repository privato separato** (per esempio `chi-fa-cosa-dati`), che la pagina legge e scrive con l'API di GitHub.

## Primo collegamento (una volta per dispositivo)

1. Su GitHub: **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. **Repository access**: *Only select repositories* → il repository dei dati.
3. **Permissions → Repository permissions → Contents**: *Read and write*.
4. Apri la pagina, sezione **Collegamento a GitHub**: scrivi il repository dei dati (`utente/chi-fa-cosa-dati`) e incolla il token.

Il token resta salvato solo nel browser di quel dispositivo. "Scollega questo dispositivo" lo cancella.

## Come sono salvati i dati

Nel repository dei dati:

- `impostazioni.json`: i nomi delle due persone e della bambina.
- `giorni/AAAA-MM.json`: un file per mese, con un elemento per ogni giorno (compiti, chi li ha fatti, minuti, extra, asilo sì/no, bagnetto sì/no).

Ogni modifica è un commit, quindi su GitHub si vede la storia di tutto quello che è stato segnato. La pagina si aggiorna da sola ogni 30 secondi.

## Cosa fa

- Compiti divisi per momento della giornata: Mattina, Casa (Bucato, Cucina, Spazzatura, Extra), Pomeriggio, Pranzo e cena, Sera.
- "C'è asilo oggi?" e "Bagnetto stasera?" mostrano i compiti giusti per quel giorno.
- Per ogni compito si segna chi l'ha fatto e i minuti reali; per l'intrattenimento nei giorni senza asilo si segnano gli orari.
- Attività extra con minuti liberi.
- Riassunto del giorno da copiare e condividere.
- Cancellazione dei dati di un giorno, con conferma.
