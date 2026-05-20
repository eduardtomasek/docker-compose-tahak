# Build cache a BuildKit — plán

## Cíl

Doplnit sekci vysvětlující, proč se buildy chovají rychle nebo pomalu, jak funguje invalidace cache a co navíc přináší BuildKit.

## Co má sekce pokrýt

- co je BuildKit a Buildx
- jak funguje build cache
- invalidace cache
- řazení instrukcí podle volatility
- `RUN --mount=type=cache`
- build secrets a SSH mounts
- external cache backends
- multi-stage a multi-platform jako související patterny

## Navržená struktura v taháku

1. Co je BuildKit
2. Jak funguje cache
3. Co cache invaliduje
4. Praktické optimalizační patterny
5. Secrets / SSH / cache mounts
6. CI/CD cache a external backends

## Primární zdroje

- Docker Docs — BuildKit  
  https://docs.docker.com/build/buildkit/
- Docker Docs — Docker Build overview  
  https://docs.docker.com/build/concepts/overview/
- Docker Docs — Docker build cache  
  https://docs.docker.com/build/cache/
- Docker Docs — Using the build cache  
  https://docs.docker.com/get-started/docker-concepts/building-images/using-the-build-cache/
- Docker Docs — Build cache invalidation  
  https://docs.docker.com/build/cache/invalidation/
- Docker Docs — Cache storage backends  
  https://docs.docker.com/build/cache/backends/
- Docker Docs — Build secrets  
  https://docs.docker.com/build/building/secrets/
- Docker Docs — Multi-stage builds  
  https://docs.docker.com/build/building/multi-stage/
- Docker Docs — Docker Build  
  https://docs.docker.com/build/

## Poznámky k implementaci

- Sekci nezahlcovat interní teorií LLB víc než je potřeba.
- Preferovat praktické vysvětlení nad implementační detaily.
