# Dashboard-mobile
Creazione di una dashboard Home Assistant pensata appositamente per uso da cellulare.

## Contenuto

- [`dashboard-mobile.yaml`](./dashboard-mobile.yaml) — configurazione Lovelace completa, pronta da importare.

## Struttura pensata per il telefono

- **5 viste** (Casa, Luci, Clima, Sicurezza, Energia) invece di un'unica pagina lunghissima: su mobile Home Assistant le mostra come barra di navigazione in basso, comoda da usare con il pollice.
- **Card `tile`** con controlli rapidi integrati (slider luminosità, modalità clima, apri/chiudi tapparelle...) così non serve aprire il pop-up di dettaglio per le azioni più comuni.
- **Griglie a 1-2 colonne**: bottoni e card grandi, facili da toccare.
- **Scene e preferiti in cima** alla prima vista ("Casa"): le azioni usate più spesso (spegni tutto, buonanotte, termostato, porta d'ingresso, allarme) sono a un tocco dall'apertura dell'app.

## Come importarla

1. In Home Assistant: **Impostazioni → Dashboard → Aggiungi dashboard → Nuova dashboard da zero**. Dai un `url_path` con un trattino (es. `casa-mobile`).
2. Apri la nuova dashboard, tocca la matita (**Modifica dashboard**) → menu **⋮** → **Modifica in YAML**.
3. Cancella il contenuto proposto e incolla tutto quello di `dashboard-mobile.yaml`.
4. Salva.

## Personalizzazione

Il file contiene entità segnaposto marcate con `# <-- SOSTITUISCI`. Sostituiscile con le tue entità reali:

- Trovi gli ID esatti in **Impostazioni → Dispositivi e servizi → Entità** (o cercandoli nel pannello Sviluppatore → Stati).
- Se non possiedi un dominio (es. nessun allarme o nessuna telecamera), elimina semplicemente la card o l'intera vista corrispondente.
- Gli script `script.buonanotte` e `script.sono_a_casa` vanno creati separatamente in **Impostazioni → Automazioni e scene → Script**, oppure puoi rimuovere quei due bottoni scena se non ti servono.

## Estensioni consigliate (opzionali)

- [HACS](https://hacs.xyz/) + card [Mushroom](https://github.com/piitaya/lovelace-mushroom) per uno stile ancora più moderno e compatto.
- [Sezione di navigazione fissa in basso](https://www.home-assistant.io/dashboards/dashboards/) è già gestita automaticamente da Home Assistant su schermi stretti grazie alle viste multiple: nessuna configurazione aggiuntiva richiesta.
