# Sito Hepcat — landing + documenti legali

Sito statico (nessuna build, nessuna dipendenza): landing page, privacy policy
e termini di servizio in italiano (versione autorevole) e inglese (cortesia).

```
site/
  index.html        landing page
  privacy.html      privacy policy (IT)
  privacy-en.html   privacy policy (EN)
  terms.html        termini di servizio (IT)
  terms-en.html     terms of service (EN)
  assets/style.css  stile condiviso (palette Ottanio & Oro dell'app)
```

## ⚠️ Da compilare prima della pubblicazione

I segnaposto sono evidenziati in giallo nelle pagine (classe `.placeholder`):

| Dove | Cosa |
| --- | --- |
| `privacy*.html`, `terms*.html` | **Nome e cognome del titolare** del trattamento |
| `privacy*.html`, `terms*.html` | **Email di contatto/supporto** (anche nel footer di `index.html`) |
| `privacy*.html` | **Regione del progetto Supabase** (verificare nella dashboard: Settings → General) |
| `terms*.html` | **Città del titolare** (foro competente) |
| `index.html` | Link e badge ufficiali App Store / Google Play dopo la pubblicazione |

Dopo la compilazione, rimuovere la classe `placeholder` dagli `<span>` per
togliere l'evidenziazione.

## Cose da verificare prima di pubblicare

- La privacy dichiara «nessun analytics di terze parti»: resta vero finché non
  si aggiungono Sentry/analytics. In quel caso aggiornare la sezione II e IV.
- La data «Ultimo aggiornamento» va aggiornata a ogni modifica sostanziale.
- L'URL pubblico di `privacy.html` va inserito in App Store Connect e nella
  Play Console (e deve combaciare con i link in-app in `constants/legal.ts`).

## Deploy consigliato

Qualsiasi hosting statico va bene. Due opzioni gratuite:

- **GitHub Pages**: repo pubblico dedicato (es. `hepcat-site`) con questi file,
  Settings → Pages → branch `main`. URL tipo `https://<user>.github.io/hepcat-site/`.
- **Vercel/Netlify**: drag & drop della cartella `site/` o deploy da repo.

Con un dominio custom (es. `hepcat.app`) gli URL legali restano stabili anche
cambiando hosting: preferibile prima della submission negli store.
