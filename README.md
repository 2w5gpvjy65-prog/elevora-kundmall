# Elevora UF – kundmall

Mall för varje ny kundsida. Skapa ett nytt repo med **Use this template**, så får kundprojektet:
- `CLAUDE.md`: Elevoras gemensamma regler, plus en del att fylla i för kunden. Claude läser den automatiskt.
- En enkel startsida: produktsektion med Stripe-knappar, kontaktformulär (Web3Forms), tack- och 404-sida.
- Säkerhetsrubriker (`_headers`) och Cloudflare-inställningar (`wrangler.jsonc`).

## Starta ett nytt kundprojekt
1. **Use this template → Create a new repository**, döp den till t.ex. `kundnamn-site` (privat).
2. Starta en Claude-session på det nya repot och skriv: *"Nytt kundprojekt: [företag]. Fyll i DEL 2 i CLAUDE.md och bygg sidan i deras stil."*
3. Byt i koden: `KUNDNAMN`, `DOMAN.SE`, `DIN-WEB3FORMS-NYCKEL`, `DIN-PAYMENT-LINK`, `"name"` i `wrangler.jsonc`, favicon och bilder i `img/`.
4. Koppla repot till Cloudflare (Workers & Pages → Create → Import repository) för förhandsvisning på workers.dev.

## Checklista vid leverans
- [ ] Kunden har egna konton med eget mejl och tvåstegsverifiering: GitHub, Cloudflare, Stripe, Web3Forms, registrar.
- [ ] Domänen är köpt i kundens namn.
- [ ] Repot överfört: Settings → General → Danger Zone → **Transfer ownership** → kundens konto.
- [ ] Kunden har bjudit in Elevora som collaborator (GitHub) och member (Cloudflare) om de köper löpande uppdateringar.
- [ ] Kundens Cloudflare kopplat till kundens repo. Domänen tillagd (namnservrar bytta, gamla A-poster borttagna, Custom Domain för domän + www).
- [ ] Web3Forms-nyckel och Stripe Payment Links är kundens egna.
- [ ] Testköp och testformulär gjorda tillsammans med kunden.
- [ ] Mobil och dator kontrollerade.
- [ ] Offerten säger: kunden äger domän, kod och konton. Elevora får visa sidan som referens.
