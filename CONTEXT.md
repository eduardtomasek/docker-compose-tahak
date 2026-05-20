# CONTEXT

## Účel projektu

`docker-tahak` je statický HTML tahák pro Docker Compose v češtině. Repo aktuálně neobsahuje build pipeline ani aplikační framework; hlavním artefaktem je jeden samostatný soubor `docker-compose-tahak.html`.

## Struktura repozitáře

- `docker-compose-tahak.html`
  - celý produkt v jednom souboru
  - obsahuje HTML markup, inline CSS i malý inline JavaScript
- `AGENTS.md`, `CLAUDE.md`
  - pracovní instrukce pro agenty
- `.grepai`, `.serena`, `.gitnexus`, `.claude`
  - pomocná metadata a tooling

Prakticky to znamená, že obsah, vzhled i interakce se dnes mění přímo v `docker-compose-tahak.html`.

## Jak je stránka poskládaná

Stránka má tři vrstvy:

1. `head > style`
   - kompletní design systém a layout pravidla
2. `body`
   - `header` s logem a tab navigací
   - `main` s jednotlivými obsahovými sekcemi
3. spodní `script`
   - jednoduché přepínání tabů přes třídu `active`

### Hlavní HTML patterny

- Navigace používá tlačítka `.nav-btn` s atributem `data-tab="..."`.
- Každý tab má odpovídající sekci `.section` s `id="tab-..."`.
- Aktivní stav je řízen čistě přidáním/odebráním třídy `active`.
- Obsah je skládán z opakovatelných bloků:
  - `.grid`
  - `.card`
  - `.entry`
  - `.key`
  - `.desc`
  - `pre.code`

## CSS systém

CSS je aktuálně celé inline v `<style>` bloku na začátku souboru. Není tu externí stylesheet ani preprocessoring.

### Základní principy

- Design tokens jsou v `:root` jako CSS custom properties.
- Barevnost je tmavá, ve stylu GitHub dark UI.
- Typografie je rozdělená na:
  - `--sans` pro běžné UI
  - `--mono` pro ukázky příkazů a YAML
- Layout používá hlavně:
  - `flex` pro header a navigaci
  - `grid` pro obsahové karty
- Responsivita je řešená jedním breakpointem:
  - `@media (max-width: 700px)`

### Důležité CSS proměnné

- Pozadí a vrstvy: `--bg`, `--bg2`, `--bg3`, `--bg4`
- Ohraničení: `--border`, `--border2`
- Text: `--text`, `--text2`, `--text3`
- Akcenty: `--blue`, `--blue-bg`, `--green`, `--green-bg`, `--amber`, `--amber-bg`, `--red`, `--teal`
- Fonty: `--mono`, `--sans`

### Hlavní CSS stavebnice

- Reset:
  - globální `box-sizing`
  - nulování `margin` a `padding`
- Layout:
  - `header`
  - `main`
  - `.section`, `.section.active`
  - `.grid`, `.grid.wide`, `.col-full`
- UI komponenty:
  - `.logo`
  - `.nav-btn`
  - `.card`, `.card-label`
  - `.entry`, `.key`, `.desc`
  - `.tip`
  - `.badge`, `.badge-dep`, `.badge-new`
  - `.cmd-table`, `.cmd-group`
- Code styling:
  - `pre.code`
  - `.ck`, `.cv`, `.cn`, `.cc` pro ručně dělaný syntax highlight

## Jak v projektu používat a upravovat CSS

### Co dodržet

- Preferuj úpravy existujících CSS custom properties místo nahodilého přidávání nových barev.
- Pokud přidáváš nový vizuální pattern, zkus ho složit z existujících tříd `.card`, `.entry`, `.tip`, `.badge`, `.grid`.
- Zachovej tmavý vizuální jazyk a současný kontrast textu vůči pozadí.
- Pro kódové a YAML ukázky používej `pre.code` a stávající span tokeny `.ck`, `.cv`, `.cn`, `.cc`.
- Pro nový tab drž vazbu:
  - tlačítko `.nav-btn[data-tab="xyz"]`
  - sekce `#tab-xyz.section`

### Čemu se vyhnout

- Nevnášet CSS do inline `style=""` atributů v HTML, pokud to není nutné.
- Nevytvářet druhý zdroj pravdy pro barvy mimo `:root`.
- Neměnit názvy stávajících tříd bez současné úpravy HTML a JS vazeb.
- Nepřidávat další breakpointy bez důvodu; současný layout je postavený na jednoduchém single-breakpoint modelu.

### Doporučený postup při změně stylů

1. Nejdřív zjisti, jestli změna jde vyřešit přes existující proměnné nebo utility třídy.
2. Pokud ne, přidej novou třídu do tematicky správné sekce ve `<style>`.
3. Novou třídu pojmenuj podle role v UI, ne podle konkrétní barvy nebo jednorázového vzhledu.
4. Ověř desktop i mobilní stav, hlavně:
   - header
   - horizontální navigaci
   - `.grid` přechod do jednoho sloupce
   - scrollování `pre.code`

## JavaScript vazby relevantní pro CSS

Spodní script:

- hledá všechny `.nav-btn`
- po kliknutí všem odebere `.active`
- správnému tlačítku a správné `.section` ji vrátí

Z toho plyne:

- `active` je funkční třída, ne jen vizuální dekorace
- pravidla `.section` a `.section.active` jsou kritická pro fungování navigace
- přejmenování `.nav-btn`, `.section` nebo `active` by rozbilo přepínání tabů

## Aktuální pracovní realita

- Nejsou nalezené build skripty, testy ani lint konfigurace.
- Projekt se v současném stavu chová jako single-file statická stránka.
- Při významnějších změnách dává smysl doplnit jednoduchou dokumentaci k UI patternům sem do `CONTEXT.md`, dokud neexistuje samostatný docs adresář.
