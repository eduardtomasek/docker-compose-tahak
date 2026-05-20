# Docker Runtime Sections

## Proč

Po sekcích `Dockerfile` a `Docker image` chyběla v taháku provozní část:

- co je container
- jak řešit data a mounty
- jak funguje networking
- jak funguje BuildKit a cache
- jak se image distribuují
- jak Docker debugovat
- jak udělat základní security hardening

Bez toho byl tahák silný v syntaxi, ale slabší v mentálním modelu a běžném provozu.

## Co přibylo

- `Container`
- `Storage`
- `Networking`
- `BuildKit`
- `Registry`
- `Troubleshooting`
- `Security`

## Zásady implementace

- Sekce drží existující single-file UI a stejné stavebnice:
  - `tip`
  - `grid`
  - `card`
  - `entry`
  - `pre.code`
  - `cmd-table`
- Obsah je opřený primárně o oficiální Docker dokumentaci.
- Ke každé nové sekci existuje samostatný implementační plán v `plans/` se seznamem zdrojů.

## Záměr

Cílem není nahradit dokumentaci Dockeru, ale vytvořit rychlý orientační tahák, který propojí:

- build
- image
- container runtime
- storage
- networking
- distribuci
- troubleshooting
- security
