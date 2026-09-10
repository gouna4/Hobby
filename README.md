# Klusboek

Klussen, klanten en bonnetjes bijhouden voor een klusjesman. Per klant zoveel
klussen als je wilt, met wat je voor het werk vraagt en wat de materialen
kosten. Bonnetjes maak je met de camera van je telefoon.

**Geen server, geen account, geen internet nodig.** Wat je invult blijft in de
opslag van de browser op je eigen toestel en wordt nergens naartoe gestuurd.
Deze bestanden zijn leeg: wie de site opent, krijgt een leeg boek.

De app staat standaard in het Arabisch. Met de knop rechtsboven (`NL` / `ع`)
wissel je naar het Nederlands en terug.

## Wat het bijhoudt

- Klanten met telefoonnummer, plaats en een notitie
- Per klant zoveel klussen als nodig, met een datum en een omschrijving
- Drie standen per klus: moet nog, bezig, klaar
- Wat je voor het werk vraagt, apart van wat de materialen kosten
- Materialen als lijst: per regel wat je gekocht hebt en wat het kostte,
  met een plusje voor de volgende
- Een foto van het bonnetje bij elke materiaalregel, gemaakt met de camera
- Betalingen per klus, ook als er in delen betaald wordt, en wat er nog
  openstaat
- Dirham of euro als hoofdmunt, met een instelbare koers en de andere munt
  eronder. Per bedrag kun je kiezen: DH of €
- Meerdere klussen bij een klant aanvinken; onderin staat meteen wat die
  samen kosten
- Van die aangevinkte klussen een overzicht maken en dat via WhatsApp of het
  deelmenu naar de klant sturen, in het Arabisch of het Nederlands
- Aangevinkte klussen in één tik op betaald zetten
- Bovenaan: wat er nog te krijgen is, wat er deze maand binnenkwam en hoeveel
  klussen nog niet betaald zijn
- Een knop om alle bedragen te verbergen, en een cijferslot van vier cijfers
- Back-up maken en terugzetten, en vijf herstelpunten op het toestel zelf

## Bestanden

    index.html        de hele app: opmaak en code in één bestand
    sw.js             offline werken; eerst het netwerk, dan de eigen kopie
    manifest.json     maakt hem installeerbaar op je beginscherm
    icon-192.png      pictogram
    icon-512.png      pictogram

## Een nieuwe versie uitbrengen

Verhoog het nummer op twee plekken, anders zie je je eigen wijziging niet:

1. `index.html` — `var VERSIE='4'` bovenaan het script
2. `sw.js` — `klusboek-v4`

De regel onderaan de instellingen haalt het nummer daar zelf op.

## Bonnetjes

Het boek zelf staat in `localStorage` en die lade is maar zo'n 5 MB groot:
daar past geen foto in. De foto's van de bonnetjes gaan daarom in IndexedDB,
een tweede lade op het toestel die voor bestanden bedoeld is. Ze worden bij
het toevoegen verkleind naar ongeveer 1500 pixels en opnieuw opgeslagen als
JPEG, zo'n 200 KB per stuk.

**Ze zitten niet in het back-upbestand.** Dat is tekst; een foto niet. Een
back-up terugzetten geeft je je boek terug, niet je bonnetjes. Wil je een
bonnetje bewaren, tik het dan aan en gebruik Sturen.

## Nooit in deze repo

Het back-upbestand uit de instellingen (`klusboek-JJJJ-MM-DD.json`). Daarin
staan klantnamen, telefoonnummers en bedragen. `.gitignore` houdt ze tegen,
maar kijk voor het uploaden of er niets tussen zit.

## Let op

De gegevens hangen aan het webadres. Verhuis je de app naar een ander adres,
maak dan eerst een back-up en zet die daarna terug via de instellingen.
