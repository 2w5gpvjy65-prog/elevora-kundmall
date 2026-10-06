# Elevora UF – kundprojekt

Det här repot är en webbsida som **Elevora UF** bygger åt en kund. Läs hela filen innan du gör något.
Övre delen innehåller Elevoras gemensamma regler och är samma i alla kundprojekt. Nedre delen innehåller kundens egna uppgifter.

---

## DEL 1: Elevoras gemensamma regler (ändra inte per kund)

### Vilka vi är
- Elevora UF: ett UF-företag med tre killar från gymnasiet i Mora, Dalarna. Bygger hemsidor och webbshoppar åt UF-företag och små varumärken i hela Sverige.
- Kontakt: elevora.uf@gmail.com · elevorauf.se
- Vi använder AI (Claude) men granskar allt själva. Leverans på 1–2 veckor.

### Så vill användaren ha svar
- **Svenska**, kort, med **enkla steg-för-steg-instruktioner** om exakt var man ska trycka. Användaren sitter ofta på mobilen och skickar skärmdumpar.
- Testa i både mobil och dator, och ta skärmdumpar, innan något sägs vara klart.
- Gör saker själv när det går. Be bara användaren om det som kräver deras inloggning.
- När något nytt bestäms: uppdatera den här filen (DEL 2) i samma session.

### Arbetsgång med kunden
1. Kort gratissamtal (cirka 15 min): vad de säljer och vilken stil de vill ha.
2. Skriftlig offert med fast pris, samma vecka.
3. Första förslaget inom en vecka, förhandsvisat på en workers.dev-adress. Ändringar tills kunden är nöjd.
4. Publicering: koppla domän och betalning, gör ett testköp tillsammans med kunden.
5. Överlämning enligt checklistan i README.md.

### Priser (Elevora)
- Webbshop: UF 1 200 kr (ordinarie från 2 000 kr) · Hemsida, en sida: UF 600 kr (ordinarie 1 200 kr) · Google-profil: 400 kr · Löpande uppdateringar: 200 kr/mån.
- Kunden betalar själv domänen (cirka 200 kr/år) och betaltjänstens avgift per köp. Säg "inga månadsavgifter till oss", aldrig "gratis att ta betalt".

### Ägarskap (viktigt)
- **Kunden äger allt** på egna konton med sitt eget mejl: domän, GitHub-repo, Cloudflare, Stripe och Web3Forms.
- Elevora bjuds in som collaborator (GitHub) och member (Cloudflare). **Inga delade lösenord, inga konton i Elevoras namn.**
- Under bygget ligger repot hos Elevora. Vid leverans görs **Transfer ownership** till kundens GitHub.
- Slutar kunden köpa uppdateringar tar de bort Elevoras åtkomst, och sidan fortsätter fungera.

### Teknik (standard för alla kunder)
- Ren statisk HTML/CSS/JS, inget byggsteg. Filer: `index.html`, `css/style.css`, `js/main.js`, `tack.html`, `404.html`, `img/`.
- **Hosting: Cloudflare Workers** med statiska filer (`wrangler.jsonc`, `.assetsignore`). Build command tomt, deploy command `npx wrangler deploy`. Publiceras automatiskt från `main`.
- **Domän**: köps av kunden (t.ex. Loopia). Lägg till domänen i kundens Cloudflare (Connect a domain, Free), byt namnservrar hos registraren, ta bort gamla A-poster, och lägg till Custom Domain för både `domän.se` och `www.domän.se` under Workers → Settings → Domains & Routes.
- **Formulär**: Web3Forms. Byt `DIN-WEB3FORMS-NYCKEL` i `index.html` mot kundens nyckel. Nyckeln är publik per design.
- **Betalning**: Stripe **Payment Links** (kort, Klarna, Swish). Knapparna länkar till Stripe, så det behövs ingen server och inga hemliga nycklar i koden. Kortuppgifter når aldrig sidan.
- Höj `?v=N` på style.css och main.js i alla HTML-filer vid ändringar, så att besökare inte ser cachade versioner.
- Lägg aldrig hemliga nycklar (t.ex. Stripes secret key) i repot.

### Säkerhet
- `_headers` innehåller säkerhetsrubriker (CSP, frame-ancestors none m.m.). Lägger man till en ny extern tjänst, till exempel ett nytt typsnitt eller ett skript, måste den läggas till i CSP:n, annars blockeras den.
- Ingen inline-JavaScript, eftersom CSP:n blockerar det. Lägg JS i `js/main.js`.
- Tvåstegsverifiering på alla konton (kundens och Elevoras). Privata repon.

### Design (Elevoras stil, anpassas efter kunden)
- Professionellt och stilrent, inte "AI-mall". Inga generiska gradienter, inga rundade standardkort överallt, inga ritade figurer i stället för foton.
- Kundens egna produktbilder, stora och snygga. Testa alltid mobilen först, eftersom kunderna kommer från Instagram och TikTok.
- Färger och typsnitt styrs från `:root` i `css/style.css`.

---

## DEL 2: Den här kunden (fyll i vid projektstart)

- **Företag:** _[namn]_ · Instagram: _[@konto]_
- **Kontaktperson:** _[namn, mejl]_
- **Säljer:** _[produkter]_
- **Tjänst och pris:** _[t.ex. Webbshop, UF-pris 1 200 kr]_
- **Domän:** _[domän.se]_ · registrar: _[Loopia/one.com]_
- **Stil:** _[färger, typsnitt, känsla, referenser]_
- **Konton (kundens):** GitHub _[ ]_ · Cloudflare _[ ]_ · Stripe _[ ]_ · Web3Forms _[ ]_
- **Status:** _[skiss / första förslag / publicerad / överlämnad]_
- **Beslut och önskemål:** _[lägg till här under projektets gång]_
