# Jouw VA Kracht Kaart live zetten in Kennis.shop

Deze map bevat:
- `index.html` — de tool zelf (jouw huisstijl)
- `api/generate.js` — het veilige tussenstukje dat met AI je samenvatting maakt
- `LEESMIJ.md` — dit stappenplan

Je hoeft niets te programmeren. Je doorloopt drie stappen: een API-sleutel ophalen, de map online zetten (Vercel), en de link embedden in Kennis.shop.

---

## Stap 1 — Haal je eigen API-sleutel op

1. Ga naar `console.anthropic.com` en log in (of maak een account).
2. Klik op **API keys** → **Create key**, geef hem een naam en kopieer de sleutel. Bewaar hem goed; je ziet hem maar één keer.
3. Zet er wat tegoed op via **Billing** (bijv. €20). Een analyse kost maar centen, dus dit gaat lang mee.

Belangrijk: deze sleutel komt in stap 2 als beveiligde instelling op Vercel te staan — nooit in de tool zelf. Zo kan niemand op jouw kosten genereren.

---

## Stap 2 — Zet de map online met Vercel

**De makkelijkste manier (zoals in de video): laat Claude Code het doen.**
Open deze map in Claude Code en geef als opdracht:
> "Zet dit project op GitHub en deploy het naar Vercel. Voeg op Vercel de environment variable `ANTHROPIC_API_KEY` toe met deze waarde: [jouw sleutel]. Geef me daarna de live-URL."

Claude Code regelt dan GitHub + Vercel + de instelling voor je.

**Liever zelf via de Vercel-website?**
1. Maak een gratis account op `vercel.com` en een gratis account op `github.com`.
2. Zet deze map in een nieuwe GitHub-repository (sleep de bestanden in een nieuwe repo via de GitHub-website, of laat Claude Code dit doen).
3. Op Vercel: **Add New… → Project → Import** je repository.
4. Voordat je op **Deploy** klikt, open je **Environment Variables** en voeg toe:
   - Name: `ANTHROPIC_API_KEY`
   - Value: jouw sleutel uit stap 1
5. Klik **Deploy**. Na een halve minuut krijg je een link, bijv. `https://va-kracht-kaart.vercel.app`.
6. Open die link en test de tool. Vul een paar vragen in en klik op "Genereer".

---

## Stap 3 — Embed in je Kennis.shop-les

Kennis.shop heeft hier een ingebouwde embed-functie voor:

1. Ga naar je **cursus** en klik op **Inhoud**.
2. Klik op het **pennetje** naast de les waar je de tool wilt plaatsen.
3. Klik op het **Embed-icoontje**.
4. Plak deze code en vervang de URL door jouw eigen Vercel-link:

```html
<iframe src="https://JOUW-LINK.vercel.app" width="100%" height="1000" style="border:0;" loading="lazy"></iframe>
```

Tip: staat de tool te kort of te lang in beeld? Pas het getal bij `height` aan (bijvoorbeeld 1200).

Je studenten blijven nu volledig in je leeromgeving — ze klikken, vullen in en krijgen hun persoonlijke VA Kracht Kaart, zonder Kennis.shop te verlaten.

---

## Lettertype

Je merklettertype **Sodabery** zit al ingebakken in `index.html` (de koppen staan er automatisch in). Je hoeft hier niets voor te doen.
