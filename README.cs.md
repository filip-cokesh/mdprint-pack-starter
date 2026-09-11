# mdprint-pack-starter

Vzorový **template pack** pro [mdprint](https://github.com/filip-cokesh/mdprint)
k forknutí — obrandujte si Markdown → tiskové HTML dokumenty vlastním logem,
barvami, fonty a patičkou (včetně social odkazů s ikonami).

*English guide: [README.md](README.md).*

**Živé demo:** [filip-cokesh.github.io/mdprint-pack-starter](https://filip-cokesh.github.io/mdprint-pack-starter/) —
Markdown zdroj vedle výsledku vysázeného tímto packem (CS/EN/DE).

Pack je obyčejná složka načítaná za běhu — mdprint se nepřekládá:

```
pack.toml          identita: [pack] name, [company] patička, [[links]], [[fonts]]
template.css       vzhled: akcentová barva, fonty, hlavička/patička, tisk
logo-light.png     logo pro světlý režim a tisk (volitelné)
logo-dark.png      logo pro tmavý režim (volitelné)
icons/github.svg   ikona odkazu v patičce, inlinuje se do HTML (volitelné)
```

Vyzkoušení hned teď:

```
mdprint --template cesta\k\mdprint-pack-starter dokument.md
```

Odkazy v patičce (`[[links]]`) vyžadují **mdprint ≥ 0.4.0**.

## Přizpůsobení krok za krokem

1. **Use this template** (tlačítko nahoře) nebo fork, pak naklonovat.
2. **Loga** — vyměňte `logo-light.png` (světlé pozadí + tisk)
   a `logo-dark.png` (tmavé pozadí). Velikost libovolná, škáluje ji
   `template.css`. Bez loga? Oba soubory smažte — v hlavičce zůstane název.
3. **Akcentová barva** — v `template.css` nastavte `--brand-accent`
   (a barvy odkazů) na třech místech: světlý režim a dva tmavé bloky
   (tam *světlejší* stupeň téhož odstínu; cílem je kontrast ≥ 4,5:1 na obou
   pozadích).
4. **Patička** — vyplňte `[company]` v `pack.toml`; nepotřebná pole smažte.
   Každé pole jde navíc přebít per projekt z `mdprint.toml`.
5. **Odkazy** — upravte bloky `[[links]]`: label, URL, volitelně `icon`
   (SVG/PNG uvnitř packu; monochromatické ikony se v tmavém režimu samy
   invertují do bílé).
6. **Fonty** — buď embedujte WOFF2 přes `[[fonts]]` (**jen pokud licence
   fontu dovoluje redistribuci** — soubory se base64 inlinují do každého
   vygenerovaného HTML), nebo font jen pojmenujte v `--font-sans`
   v `template.css` a u čtenářů bez něj se použije fallback (bezpečná volba
   pro licencované firemní fonty).
7. Přejmenujte pack v `[pack] name` a spusťte
   `mdprint --template . dokument.md` na zkušebním souboru. Zkontrolujte
   světlý režim, tmavý režim (přepínač ◐) i náhled tisku (Ctrl+P).

## Ochranné známky

- GitHub mark (`icons/github.svg`, z [Octicons](https://github.com/primer/octicons),
  MIT) je ochranná známka GitHub, Inc.; užit dle
  [GitHub logo guidelines](https://github.com/logos) jako social tlačítko
  odkazující na GitHub. Odkazujete-li jinam, použijte ikonu dané služby
  a řiďte se jejími pravidly.
- Logo mdprint v `logo-light.png` / `logo-dark.png` patří projektu
  mdprint — ve svém packu ho nahraďte vlastní grafikou.

## Licence

MIT — viz [LICENSE](LICENSE). Výhrady k ochranným známkám výše.
