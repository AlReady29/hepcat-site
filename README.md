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

## ⚠️ Da compilare prima della submission

Compilati (2026-06-12): titolare **Alessandro Di Già**, regione Supabase
**UE — Francoforte (eu-central-1)**, foro di **Roma**.

Segnaposto rimanenti, evidenziati in giallo nelle pagine (classe `.placeholder`):

| Dove | Cosa |
| --- | --- |
| `privacy*.html`, `terms*.html` | **Email di contatto/supporto dedicata** (anche nel `mailto:` del footer di `index.html`) — da creare, vedi nota sotto |
| `index.html` | Link e badge ufficiali App Store / Google Play dopo la pubblicazione |

Email: decisione presa per una casella **dedicata** (non quella personale),
idealmente su dominio custom (es. `supporto@hepcat.app` con Cloudflare Email
Routing). Dopo la creazione, sostituire e rimuovere la classe `placeholder`.

## Cose da verificare prima di pubblicare

- La privacy dichiara «nessun analytics di terze parti»: resta vero finché non
  si aggiungono Sentry/analytics. In quel caso aggiornare la sezione II e IV.
- La data «Ultimo aggiornamento» va aggiornata a ogni modifica sostanziale.
- L'URL pubblico di `privacy.html` va inserito in App Store Connect e nella
  Play Console (e deve combaciare con i link in-app in `constants/legal.ts`).

## Deploy

Il sito è pubblicato su **GitHub Pages** dal repo pubblico
[`AlReady29/hepcat-site`](https://github.com/AlReady29/hepcat-site)
(branch `main`, root): <https://already29.github.io/hepcat-site/>.

**Questa cartella è la fonte di verità.** Per aggiornare il sito:

```bash
git clone https://github.com/AlReady29/hepcat-site.git /tmp/hepcat-site-deploy
cp -R site/ /tmp/hepcat-site-deploy/
cd /tmp/hepcat-site-deploy && git add -A && git commit -m "Aggiorna sito" && git push
```

Gli URL sono referenziati in `constants/legal.ts` e andranno dichiarati in App
Store Connect e Play Console. Con un dominio custom (es. `hepcat.app`) gli URL
legali restano stabili anche cambiando hosting: valutarlo prima della
submission negli store.
