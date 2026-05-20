# Registry a distribuce — plán

## Cíl

Doplnit sekci o tom, jak se image pojmenovávají, autentizují, pushují, pullují a jak se distribuují přes registry i bez nich.

## Co má sekce pokrýt

- naming convention image references
- Docker Hub vs self-hosted/private registry
- `docker login`
- `docker image tag`
- `docker image push`
- `docker image pull`
- digest pinning
- multi-platform nuance
- save/load bez registru jako shrnutí a propojení na image sekci

## Navržená struktura v taháku

1. Jak vypadá image reference
2. Registries
3. Login, tag, push, pull
4. Tag vs digest
5. Praktické flow pro release
6. Offline a air-gapped distribuce

## Primární zdroje

- Docker Docs — docker image  
  https://docs.docker.com/reference/cli/docker/image/
- Docker Docs — docker login  
  https://docs.docker.com/reference/cli/docker/login/
- Docker Docs — docker image push  
  https://docs.docker.com/reference/cli/docker/image/push/
- Docker Docs — docker image pull  
  https://docs.docker.com/reference/cli/docker/image/pull/
- Docker Docs — Build, tag, and publish an image  
  https://docs.docker.com/get-started/docker-concepts/building-images/build-tag-and-publish-an-image/
- Docker Docs — docker image save  
  https://docs.docker.com/reference/cli/docker/image/save/
- Docker Docs — docker image load  
  https://docs.docker.com/reference/cli/docker/image/load/

## Poznámky k implementaci

- Nepoužívat registry-specific doporučení, která nejsou v oficiálních zdrojích.
- Tag vs digest vysvětlit jasně a prakticky.
