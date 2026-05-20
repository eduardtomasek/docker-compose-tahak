# Docker Compose Tahák

Statický HTML tahák pro Docker Compose a související Docker témata v češtině.

Repo aktuálně neobsahuje build pipeline ani framework. Hlavní výstup je jedna samostatná stránka v [index.html](/Users/eddy/Work/Personal/docker-tahák/index.html).

## Co v taháku je

- základní struktura `compose.yaml`
- sekce `services`, `networks`, `volumes`, `build`, `deploy`
- CLI příkazy pro `docker compose`
- rozšířené části pro `Dockerfile`, `Docker image`, `Container`
- runtime témata: `Storage`, `Networking`, `BuildKit`, `Registry`, `Troubleshooting`, `Security`
- kompletní příklad konfigurace

## Struktura repozitáře

- [index.html](/Users/eddy/Work/Personal/docker-tahák/index.html)  
  celý produkt v jednom souboru: HTML, inline CSS i jednoduchý JavaScript pro přepínání tabů
- [docs/features](/Users/eddy/Work/Personal/docker-tahák/docs/features)  
  stručná dokumentace k větším obsahovým rozšířením
- [plans](/Users/eddy/Work/Personal/docker-tahák/plans)  
  pracovní plány pro jednotlivé tematické sekce
- [CONTEXT.md](/Users/eddy/Work/Personal/docker-tahák/CONTEXT.md)  
  poznámky k architektuře a UI patternům

## Lokální použití

Stačí otevřít [index.html](/Users/eddy/Work/Personal/docker-tahák/index.html) v prohlížeči. Je to jeden samostatný HTML soubor se vším potřebným.

Volitelně můžeš použít i jednoduchý lokální server:

```bash
python3 -m http.server 8000
```

Pak otevři `http://localhost:8000`.

## Jak upravovat obsah

- Většina změn se dělá přímo v `index.html`.
- Styly jsou v inline `<style>` bloku.
- Navigace je navázaná přes tlačítka `.nav-btn[data-tab="..."]` a sekce `#tab-...`.
- Přepínání tabů zajišťuje malý inline script na konci souboru.

## Dokumentace

Větší obsahové změny patří do `docs/features/`. Důvod rozhodnutí dokumentuj spíš jako `proč` než jako čistý seznam změn.
