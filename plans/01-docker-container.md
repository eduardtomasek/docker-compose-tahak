# Docker Container — plán

## Cíl

Doplnit sekci vysvětlující, co je container jako runtime instance image a jak vypadá jeho běžný životní cyklus i každodenní práce přes CLI.

## Co má sekce pokrýt

- rozdíl `image` vs `container`
- `create` / `run` / `start` / `stop` / `restart` / `rm`
- foreground vs detached mode
- `exec`, `logs`, `inspect`, `stats`
- restart policy
- healthcheck v runtime
- signály, timeouty, `STOPSIGNAL`, `--stop-timeout`
- praktické minipříklady

## Navržená struktura v taháku

1. Co je container
2. Životní cyklus containeru
3. Každodenní příkazy
4. Restart policy a auto-start
5. Healthcheck a stav containeru
6. Debug a inspekce

## Primární zdroje

- Docker Docs — Running containers  
  https://docs.docker.com/engine/containers/run/
- Docker Docs — docker container  
  https://docs.docker.com/reference/cli/docker/container/
- Docker Docs — docker container restart  
  https://docs.docker.com/reference/cli/docker/container/restart/
- Docker Docs — Start containers automatically  
  https://docs.docker.com/engine/containers/start-containers-automatically/
- Docker Docs — View container logs  
  https://docs.docker.com/engine/logging/
- Docker Docs — docker container stats  
  https://docs.docker.com/reference/cli/docker/container/stats/
- Docker Docs — Containers view / inspect / logs / exec / stats  
  https://docs.docker.com/desktop/use-desktop/container/

## Poznámky k implementaci

- Držet text stručný a praktický.
- Nevymýšlet pojmy mimo dokumentaci.
- Přidat jen takové workflow příkazy, které jsou přímo dohledatelné v uvedených zdrojích.
