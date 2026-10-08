# Gestionale Lapidi

*Scroll down for English version*

Gestionale interno per un'azienda di lavorazione lapidi: dalla richiesta del cliente all'ordine ai fornitori, fino al montaggio in cimitero.

**Il problema —** tutte le pratiche erano gestite su fogli di carta compilati a mano:
- copia unica dei dati, consultabile da una persona alla volta
- rischio concreto di perdere o smarrire il foglio
- scrittura a mano, spesso poco leggibile
- modifiche e aggiornamenti sporchi e difficili da ricostruire
- nessuna possibilità di ricerca, filtro o storico

**La soluzione —** un'applicazione web installata sul server dell'ufficio, accessibile da tutti i PC in rete locale:
- dati centralizzati in un unico archivio, sempre aggiornati e consultabili da più postazioni contemporaneamente
- pratiche modificabili in qualsiasi momento, senza cancellature
- ricerca e filtri immediati su tutto lo storico
- backup automatici a intervalli regolari, e l'intero archivio si copia come un singolo file
- stampa automatica del modulo di lavorazione per il laboratorio

Il programma è stato sviluppato interamente da me con strumenti di AI coding (Claude Code).

## ⚠️ Disclaimer

Tutti i nomi, indirizzi, numeri di telefono e importi visibili negli screenshot sono **dati di fantasia**, inseriti appositamente per questa presentazione. Nessun dato reale dei clienti è mostrato in questo repository.

## Funzionalità

### 1. Pratiche in corso
Vista d'insieme dei lavori aperti, con cliente, cimitero e data. Un pallino colorato mostra a che punto è ogni pratica, calcolato dal programma in base alle spunte delle voci: **rosso** = da ordinare, **giallo** = ordinata (tutte le voci ordinate), **verde** = arrivata (tutte le voci arrivate). Accanto a ogni riga, un pulsante per archiviarla fra le consegnate e uno per eliminarla.

"Crea pratica" apre subito una scheda nuova, pronta da compilare. Se si esce senza scrivere nulla, la scheda vuota viene scartata da sola.

![Pratiche in corso](README/1%20-%20home%20page.png)

### 2. Ricerca e filtri
Ricerca per nome della pratica o del cliente, intervallo di date, cimitero, tipo di lapide (loculo, cippo, ossario) e stato. I filtri si combinano fra loro.

Il cimitero si cerca scrivendo: bastano poche lettere per vedere solo i cimiteri che le contengono. Lo stesso cimitero scritto in modi diversi ("Certosa", "Cimitero della Certosa") compare una volta sola.

![Filtri](README/2%20-%20filtro%20pratiche.png)

### 3. Fornitori
Elenco dei fornitori con telefono, email e note, con ricerca per nome. Un clic su una riga apre la scheda per modificarlo; "Nuovo fornitore" lo aggiunge. I fornitori si scelgono poi da un menu per ogni accessorio ordinato.

![Fornitori](README/3%20-%20fornitori.png)

### 4. Scheda pratica
Il cuore del programma, tutto in una schermata:
- **Ubicazione e cliente**: cimitero, loculo, tipo di lapide, dati anagrafici e contatti.
- **Epigrafe**: tipo (incisa, applicata o targa), carattere e testo, mostrato centrato come apparirà sulla lapide. Accanto, il conteggio di lettere e segni di punteggiatura, utile per il preventivo.
- **Accessori**: foto, cornici, vasi, lampade… ognuno con fornitore, prezzo e le spunte "ordinato" e "arrivato".
- **Manodopera e totale**: il costo di montaggio si scrive a mano, il **totale si calcola da solo** mentre si digitano gli importi.
- **Note e foto**: appunti liberi e foto caricate direttamente nella pratica.

Ogni campo resta sempre modificabile e **si salva da solo** appena lo si lascia: non ci sono pulsanti "Salva", e una piccola scritta in alto conferma il salvataggio. Lo stato della pratica si aggiorna da solo seguendo le spunte.

Con "Rinomina" si può dare alla pratica un nome a scelta, diverso da quello del cliente; lo stesso nome viene dato anche alla cartella delle sue foto.

![Scheda pratica](README/4%20-%20pratica.png)

### 5. Stampa del modulo
Da ogni pratica si genera un foglio di riepilogo pronto per la stampa, da consegnare in laboratorio: ubicazione, cliente, epigrafe, preventivo con lo stato di ogni voce, totale e note.

![Stampa modulo](README/5%20-%20stampa.png)

### 6. Pratiche consegnate
Una lapide consegnata si archivia con un clic: esce dall'elenco principale e passa nella sezione **Consegnate**, dove restano i lavori già finiti ma non ancora pagati, con l'importo di ciascuno e in alto il **totale ancora da incassare**. Anche qui funzionano ricerca e filtri. Quando il pagamento arriva, la pratica si elimina; se serve, si riporta fra quelle in corso.

![Pratiche consegnate](README/6%20-%20consegnate.png)

## Tecnologie

Node.js/Express · database SQLite · interfaccia HTML/CSS/JavaScript senza framework · rete locale, nessun accesso da remoto.

---

<br>

---

# Gestionale Lapidi (Headstone Management)

Internal management software for a headstone company: from the client's request, to supplier orders, up to the final installation at the cemetery.

**The problem —** every job was handled on paper forms filled in by hand:
- a single copy of the data, usable by one person at a time
- real risk of losing or misplacing the sheet
- handwriting, often hard to read
- messy edits and updates, impossible to reconstruct
- no search, no filters, no history

**The solution —** a web application installed on the office server, accessible from every PC on the local network:
- centralized data, always up to date and available from several workstations at once
- jobs editable at any time, with no crossing-out
- instant search and filters across the whole archive
- automatic backups at regular intervals, and the whole archive copies as a single file
- automatic printout of the workshop form

The software was developed entirely by me using AI coding tools (Claude Code).

## ⚠️ Disclaimer

All names, addresses, phone numbers and prices shown in the screenshots are **fictitious**, entered specifically for this presentation. No real client data appears in this repository.

## Features

### 1. Jobs in progress
An overview of the open jobs, with client, cemetery and date. A colored dot shows how far each job has got, worked out by the program from the items' checkboxes: **red** = to be ordered, **yellow** = ordered (every item ordered), **green** = arrived (every item arrived). Each row has a button to archive it among the delivered jobs and one to delete it.

"Crea pratica" (new job) opens a fresh job page right away, ready to fill in. If you leave without typing anything, the empty job is thrown away automatically.

![Jobs in progress](README/1%20-%20home%20page.png)

### 2. Search and filters
Search by job or client name, and narrow down by date range, cemetery, headstone type (niche, upright, ossuary) and status. Filters combine with each other.

The cemetery is found by typing: a few letters are enough to list only the cemeteries that contain them. The same cemetery written in different ways ("Certosa", "Cimitero della Certosa") shows up only once.

![Filters](README/2%20-%20filtro%20pratiche.png)

### 3. Suppliers
Suppliers with phone, email and notes, searchable by name. Click a row to edit it; "Nuovo fornitore" adds a new one. Suppliers are then picked from a menu for each ordered accessory.

![Suppliers](README/3%20-%20fornitori.png)

### 4. Job page
The core of the application, all on one screen:
- **Location and client**: cemetery, plot, headstone type, personal and contact details.
- **Epitaph**: type (engraved or applied letters), lettering style and text, shown centered the way it will look on the stone. Next to it, a count of letters and punctuation marks, used for the quote.
- **Accessories**: photos, frames, vases, lamps… each with supplier, price and "ordered" / "arrived" checkboxes.
- **Labor and total**: the installation cost is typed by hand, the **total updates by itself** as amounts are typed.
- **Notes and photos**: free notes and photos uploaded straight into the job.

Every field stays editable and **saves itself** as soon as you leave it: there are no "Save" buttons, and a small label at the top confirms the save. The job status also updates by itself, following the checkboxes.

"Rinomina" (rename) gives the job a custom name, different from the client's; the job's photo folder takes the same name.

![Job page](README/4%20-%20pratica.png)

### 5. Printable form
Each job generates a print-ready summary sheet for the workshop: location, client, epitaph, quote with the status of every item, total and notes.

![Printable form](README/5%20-%20stampa.png)

### 6. Delivered jobs
A delivered headstone is archived with one click: it leaves the main list and moves to the **Consegnate** (delivered) section, which holds work already finished but not yet paid for, with each job's amount and, at the top, the **total still to collect**. Search and filters work here too. Once the payment comes in the job is deleted; if needed, it can be moved back among the jobs in progress.

![Delivered jobs](README/6%20-%20consegnate.png)

## Built with

Node.js/Express · SQLite database · plain HTML/CSS/JavaScript frontend, no framework · local network only, no remote access.
