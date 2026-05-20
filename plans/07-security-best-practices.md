# Security best practices — plán

## Cíl

Doplnit sekci shrnující bezpečnostní doporučení pro image, containery a Docker runtime, s důrazem na věci, které uživatel skutečně nastavuje v Dockerfile, `docker run` a Compose.

## Co má sekce pokrýt

- rootless mode
- běh bez root usera v containeru
- redukované capabilities
- minimal / distroless image
- secrets místo ARG/ENV
- read-only filesystem a writable výjimky
- skenování image přes Docker Scout
- registry auth a access hygiene na vysoké úrovni

## Navržená struktura v taháku

1. Základní principy
2. Runtime hardening
3. Image hardening
4. Secrets
5. Vulnerability scanning
6. Praktické checklisty

## Primární zdroje

- Docker Docs — Security for developers  
  https://docs.docker.com/security/
- Docker Docs — Docker Engine security  
  https://docs.docker.com/engine/security/
- Docker Docs — Rootless mode  
  https://docs.docker.com/engine/security/rootless/
- Docker Docs — Rootless tips  
  https://docs.docker.com/engine/security/rootless/tips/
- Docker Docs — Minimal or distroless images  
  https://docs.docker.com/dhi/core-concepts/distroless/
- Docker Docs — Build secrets  
  https://docs.docker.com/build/building/secrets/
- Docker Docs — docker scout cves  
  https://docs.docker.com/reference/cli/docker/scout/cves/
- Docker Docs — Docker Scout image analysis  
  https://docs.docker.com/scout/image-analysis/
- Docker Docs — docker container run  
  https://docs.docker.com/reference/cli/docker/container/run/

## Poznámky k implementaci

- Neslibovat “bezpečnost” absolutně; držet se formulací typu “reduces risk”, “mitigates”.
- Kde jde, navázat na už existující sekce `Dockerfile`, `Image` a budoucí `Container`.
