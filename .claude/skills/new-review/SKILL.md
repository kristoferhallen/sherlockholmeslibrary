---
name: new-review
description: Lägg in en ny bokrecension på Sherlock-sajten (sherlock.kristoferhallen.com). Använd när Kristofer ger en recensionstext, ett betyg eller en ny bok att lägga upp, eller vill göra om en oläst bok i en guide till en recension.
---

# Ny recension

Kristofer skriver texten och sätter betyget. Claude sköter resten och
frågar hellre än gissar. Kommunicera på svenska; sajten är på engelska.

## 1. Samla in

- Recensionstexten och betyget (0–10). Ändra inte i texten utöver uppenbara
  stavfel, och fråga först om något är oklart.
- Bokens titel och författare. Kontrollera stavning av namn mot förlaget
  eller Open Library (exempel: Caiden Cooper **Myles**, inte Miles).
- Utgivningsår och, om boken ingår i en serie, seriens namn och nummer.
  Kontrollera, gissa aldrig.

## 2. Skapa recensionen

- Finns boken redan som oläst i `content/unread/<slug>/`? Flytta då mappen
  med `git mv content/unread/<slug> content/posts/<slug>` så att omslaget
  följer med, och fyll på fälten nedan.
- Annars: skapa `content/posts/<slug>/index.md`. Slug = titeln i gemener
  med bindestreck (behåll å, ä, ö och accenter som i övriga recensioner).
- Front matter, i samma ordning som befintliga recensioner:
  `author`, `author_last`, `book_title`, `date` (dagens datum),
  `grade`, `tags`, `title`, `description`, och vid serie `series`,
  `series_order`, `publication_year`, sist `cover` (`image: cover.jpg`,
  `relative: true`).
- `description`: en mening om handlingen, i stil med de andra
  ("Review of X by Y — …").
- Taggar: återanvänd befintliga (`grep -h "^- " content/posts/*/index.md | sort | uniq -c`).
  Lägg `sherlock-meets` om en känd figur från historien eller fiktionen
  förekommer.

## 3. Omslag

- Använd Kristofers bild om han har en. Annars: leta upp samma utgåva
  (Open Library, förlaget, Amazon via ISBN) och visa den för honom innan du
  sparar den.
- Minst cirka 400 px bred. Spara som `cover.jpg` i recensionens mapp.
- Bilder från förlag är ofta kvadratiska med vit kant: beskär (Pillow i en
  venv i scratchpad, Pillow finns inte globalt).

## 4. Koppla ihop

- **Serie:** finns det en guide för serien (`content/guides/`, fältet
  `guide_series`)? Då räcker det att `series` matchar exakt. Finns ingen
  guide och serien har flera böcker: fråga om en ny guide ska skapas (med
  de övriga böckerna som olästa i `content/unread/`).
- **Sherlock Meets:** för varje känd figur i boken, lägg till recensionen
  under `books` i `data/sherlockmeets.yaml`, eller skapa en ny person
  (`name`, `group`, `description`, `image`, `books`, `wikipedia`).
  Porträtt gör Kristofer själv; se minnet om porträtt för hur de rensas.
- **Inte en bok** (t.ex. ett Lego-set): sätt `not_a_book: true`.

## 5. Kontrollera

- `hugo --minify -d <scratchpad>` utan varningar.
- Titta på recensionen, guiden (om serie) och Sherlock Meets i
  förhandsvisningen (`.claude/launch.json`, `sherlock-hugo`).

## 6. Publicera

- Visa vad som ändrats och fråga innan commit och push.
- Efter push: vänta på `gh run watch` och kontrollera adressen med `curl`.
- Påminn om att lägga upp recensionen på Bluesky och erbjud ett utkast
  (titel, författare, en rad om boken, betyg, länk). Klicka aldrig Post
  utan uttryckligt ok.
