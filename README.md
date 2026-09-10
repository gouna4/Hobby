# Klusboek

Klussen, klanten en bonnetjes bijhouden voor een klusjesman. Per klant zoveel
klussen als je wilt, met wat je voor het werk vraagt en wat de materialen
kosten. Bonnetjes maak je met de camera van je telefoon.

**Geen server, geen account, geen internet nodig.** Wat je invult blijft in de
opslag van de browser op je eigen toestel en wordt nergens naartoe gestuurd.
Deze bestanden zijn leeg: wie de site opent, krijgt een leeg boek.

De app staat standaard in het Arabisch. Met de knop rechtsboven (`NL` / `ع`)
wissel je naar het Nederlands en terug.

## Hoe het in elkaar zit

Drie lagen: een **klant** heeft **opdrachten**, en in een opdracht zitten de
**klusjes**. Zo hoort alles wat bij één afspraak hoort bij elkaar.

Het geld hangt aan de opdracht. Daar spreek je een prijs af voor het werk en
daar wordt betaald. Wat een los klusje kost mag je er per klus bij zetten; de
app laat dan zien of dat samen uitkomt op wat je hebt afgesproken, en hoeveel
je nog te verdelen hebt. Vul je bij de opdracht geen prijs in, dan telt de app
gewoon de losse bedragen bij elkaar op.

Een klus mag zelf ook weer uit **onderdelen** bestaan: losse regels die je
afvinkt en die elk een eigen bedrag mogen hebben. Dezelfde regel geldt daar:
zet je bij de klus een bedrag, dan telt dat; anders telt de app de onderdelen
op. Zo kun je twaalf klusjes tot één klus samenvoegen zonder ze kwijt te
raken als afvinkbare lijst.

Materialen en bonnetjes horen bij een klus, want daar koop je ze voor. Ze
tellen vanzelf op naar de opdracht.

**Nog te krijgen telt alleen werk dat af is.** Een klus die nog op *Moet nog*
of *Bezig* staat is geen geld maar planning, en staat bovenaan apart als
*Werk in de planning*. Materialen tellen wel meteen mee: die heb je immers
voorgeschoten. Staat alles van een opdracht op klaar, dan geldt de prijs die
je hebt afgesproken; anders tellen alleen de klussen die af zijn.

## Wat het bijhoudt

- Klanten met telefoonnummer, plaats en een notitie
- Opdrachten per klant, met een afgesproken prijs en de betalingen
- Een opdracht splitsen: het afgeronde werk blijft staan om te factureren, de
  rest verhuist naar een vervolgopdracht. Het bedrag komt daarna uit de klussen
  zelf, dus een afgesproken totaalprijs vervalt bij het splitsen
- Elke opdracht doorloopt vier fasen: mee bezig, opgeleverd, factuur verstuurd,
  betaald. Een knop zet hem naar de volgende
- Het hokje voor een klus betekent klaar; wil je klussen kiezen om samen te
  voegen of te delen, zet dan Klussen kiezen aan
- Op het hoofdscherm vier cijfers: nog factureren, wacht op betaling, deze
  maand binnen, materialen voorgeschoten
- Bij elke klant staan zijn opdrachten er meteen onder, met hun fase
- Per opdracht zoveel klusjes als nodig, met een datum en een omschrijving
- Onderdelen binnen een klus: afvinken en per stuk een bedrag
- Tabblad **Te doen**: alles wat nog openstaat over alle klanten heen, wat het
  langst ligt bovenaan. Dit is ook het startscherm
- De stand van een klus met een tik doorzetten: moet nog, bezig, klaar. Werkt
  op de kaart en in de lijst van een opdracht
- **Lijst plakken**: plak een lijstje uit de groepsapp en elke regel wordt een
  eigen klus. Streepjes, bolletjes en nummers gaan er vanzelf af
- Terugvegen of de terugknop gaat één scherm terug in plaats van de app te
  sluiten
- Het tabblad waar je gebleven was wordt onthouden
- Een klus even vasthouden geeft een menu om hem naar een andere opdracht te
  verplaatsen. In de stand Klussen kiezen verplaats je er meerdere tegelijk,
  desnoods naar een gloednieuwe opdracht
- De vier fasen mag je in de instellingen zelf een naam geven
- Bij een opdracht kun je zowel het arbeidsbedrag als het materiaalbedrag zelf
  invullen; laat je er een leeg, dan telt de app de losse bedragen op
- Een strook bovenaan als een opdracht langer dan een maand op betaling wacht
- Een strook bovenaan als je twee weken geen back-up maakte
- Drie standen per klus: moet nog, bezig, klaar
- Wat je voor het werk vraagt, apart van wat de materialen kosten
- Soorten werk als knopjes onder het invulveld, met een plusje om er zelf
  een bij te zetten (die blijven bewaard)
- Materialen als lijst: per regel wat je gekocht hebt en wat het kostte,
  met een plusje voor de volgende
- Een foto van het bonnetje bij elke materiaalregel, gemaakt met de camera
- Betalingen per opdracht, ook als er in delen betaald wordt, en wat er nog
  openstaat
- Dirham of euro als hoofdmunt, met een instelbare koers en de andere munt
  eronder. Per bedrag kun je kiezen: DH of €
- Meerdere klussen in een opdracht aanvinken; onderin staat meteen wat die
  samen kosten, en je zet ze in een tik op klaar
- Aangevinkte klussen samenvoegen tot een klus: de oudste blijft staan, de
  andere worden onderdelen die je kunt afvinken en beprijzen, en de materialen
  met hun bonnetjes verhuizen mee. Een klus die eerder tot platte tekst was
  samengevoegd repareer je met de knop *Maak er onderdelen van*
- Van die aangevinkte klussen een overzicht maken en dat via WhatsApp of het
  deelmenu naar de klant sturen, in het Arabisch of het Nederlands
- Een opdracht in één tik helemaal op betaald zetten
- Bovenaan: wat er nog te krijgen is, wat er deze maand binnenkwam en hoeveel
  opdrachten nog niet betaald zijn
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

1. `index.html` — `var VERSIE='15'` bovenaan het script
2. `sw.js` — `klusboek-v15`

Het nummer verschijnt vanzelf onder de titel op het hoofdscherm en onderaan
de instellingen.

## Van een oud boek naar opdrachten

Tot versie 6 hing een klus rechtstreeks aan een klant en stonden de betalingen
bij de klus. Zet je zo'n back-up terug, dan zet `migreer()` alles om: per klant
één opdracht met de naam *Eerder werk*, met alle klussen erin en de betalingen
bij elkaar. Dat draait één keer, bij het opstarten en na het terugzetten.

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

Het back-upbestand uit de instellingen (`klusboek-JJJJ-MM-DD-uummss.json`). Daarin
staan klantnamen, telefoonnummers en bedragen. `.gitignore` houdt ze tegen,
maar kijk voor het uploaden of er niets tussen zit.

## Let op

De gegevens hangen aan het webadres. Verhuis je de app naar een ander adres,
maak dan eerst een back-up en zet die daarna terug via de instellingen.
