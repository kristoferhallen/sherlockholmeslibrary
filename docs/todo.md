# Att göra: Kristofer's Sherlock Holmes library

Levande lista. Bocka av eller ta bort punkter när de är klara. Den äldre
planen för affiliate-länkar m.m. finns i `docs/monetization-plan.md` på
grenen `feature/unread-affiliate-tip`.

## Sherlock Meets

- [ ] **Strukturerad data:** en `ItemList` (schema.org) över personerna med
      länkar till böckerna, som guiderna redan har.
- [ ] **Ture Sventon:** beskrivningen är en enda mening. Skriv några rader om
      hur han och Holmes möts i *Den löse skägghandlaren*.
- [ ] **Egna sidor för de största figurerna** (Dracula, Jekyll och Hyde och
      fler med många böcker), för sökningar som "Sherlock Holmes Dracula books".
      Kräver egen text per sida, annars blir de tunna.
- [ ] **Följ upp i Search Console** några veckor efter 2026-10-11: vilka
      sökord sidan visas för, och om ankarna syns som "Hoppa till".

## Omslag att leta upp (sparas som `cover.jpg` i recensionens mapp)

- [ ] Den löse skägghandlaren (Jannedal)
- [ ] En Oscariansk skandal (Sörmark)
- [ ] En skandal i Stockholm / Döden går i Stockholm (Sörmark)
- [ ] Sherlock Holmes i ny belysning (Sture Stig)
- [ ] Trepiporsproblem och bagateller (Bengtsson)
- [ ] Arsène Lupin contre Sherlock Holmes, 1re partie (Félix, seriealbum)
- [ ] Arsène Lupin v/s Sherlock Holmes (Leblanc, din utgåva)
- [ ] Mycroft and Sherlock: The Empty Birdcage (Titan 2019)
- [ ] Reply Paid (Heard 1942), oläst bok i Mr. Mycroft-guiden

## Pausat: affiliate, Ko-fi och annonsplats

Väntar på trafikanalysen. Öppna frågor (detaljer i den gamla planen):

- [ ] Amazon-marknad (amazon.co.uk eller .com) och konton: Amazon
      Associates, Bookshop.org, Adtraction/Adlibris, Ko-fi.
- [ ] ISBN i recensionernas front matter (krävs för köplänkar). Utgåvan du
      läste eller den som är lättast att köpa?
- [ ] Svenska guider: vänta på trafikdata.

## Teknik

- [ ] Lås Hugo-versionen i `.github/workflows/deploy.yml` (i dag `latest`).
- [ ] Ta bort död kod: `layouts/series/list.html`,
      `layouts/partials/book-cover.html` och `assets/css/extended_custom.css`
      (sajten använder `static/css/extended_custom.css`).
- [ ] Google Fonts på egen server, bara om integritet (GDPR) blir viktigt.
      Det kostar egen bandbredd.
