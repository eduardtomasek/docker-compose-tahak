# Debugging a troubleshooting — plán

## Cíl

Doplnit praktickou sekci s diagnostickým workflow pro nejčastější problémy při práci s containery, image a buildy.

## Co má sekce pokrýt

- container se hned vypne
- port není dostupný
- healthcheck padá
- nevidím logy / jak číst logy
- jak použít `inspect`, `stats`, `exec`
- image je moc velká
- cache se nechová podle očekávání
- volume nebo bind mount “překryl” obsah

## Navržená struktura v taháku

1. Rychlý debug flow
2. Container lifecycle problémy
3. Networking problémy
4. Storage problémy
5. Build/cache problémy
6. Příkazy první pomoci

## Primární zdroje

- Docker Docs — View container logs  
  https://docs.docker.com/engine/logging/
- Docker Docs — docker container  
  https://docs.docker.com/reference/cli/docker/container/
- Docker Docs — docker container stats  
  https://docs.docker.com/reference/cli/docker/container/stats/
- Docker Docs — Running containers  
  https://docs.docker.com/engine/containers/run/
- Docker Docs — Publishing and exposing ports  
  https://docs.docker.com/get-started/docker-concepts/running-containers/publishing-ports/
- Docker Docs — Bind mounts  
  https://docs.docker.com/engine/storage/bind-mounts/
- Docker Docs — Volumes  
  https://docs.docker.com/engine/storage/volumes/
- Docker Docs — Docker build cache  
  https://docs.docker.com/build/cache/
- Docker Docs — Troubleshoot Docker Desktop  
  https://docs.docker.com/desktop/troubleshoot-and-support/troubleshoot/
- Docker Docs — Containers view / logs / inspect / exec / stats  
  https://docs.docker.com/desktop/use-desktop/container/

## Poznámky k implementaci

- Tvrzení formulovat jako “ověř pomocí …” místo vymyšlených troubleshooting heuristik.
- Cílem je checklist, ne dlouhá esej.
