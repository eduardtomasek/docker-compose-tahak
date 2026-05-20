# Volumes a perzistence dat — plán

## Cíl

Doplnit sekci, která oddělí container writable layer od persistentního storage a vysvětlí, kdy použít volume, bind mount nebo tmpfs.

## Co má sekce pokrýt

- proč nestačí zapisovat do container layer
- named vs anonymous volume
- bind mount vs volume
- tmpfs a kdy ho použít
- mount přes `--mount` vs `-v`
- lifecycle dat
- backup / restore / migrate volume
- časté chyby: obscured files, write access, host coupling

## Navržená struktura v taháku

1. Mentální model perzistence
2. Volume vs bind mount vs tmpfs
3. Kdy co použít
4. Příklady `docker run`
5. Backup a obnova volume
6. Rizika a limity

## Primární zdroje

- Docker Docs — Storage overview  
  https://docs.docker.com/storage/
- Docker Docs — Volumes  
  https://docs.docker.com/engine/storage/volumes/
- Docker Docs — Bind mounts  
  https://docs.docker.com/engine/storage/bind-mounts/
- Docker Docs — tmpfs mounts  
  https://docs.docker.com/engine/storage/tmpfs/
- Docker Docs — Running containers / mount flags  
  https://docs.docker.com/engine/containers/run/

## Poznámky k implementaci

- Zdůraznit, že volume data žijí mimo lifecycle containeru.
- U tmpfs zmínit pouze fakta z docs: RAM-backed, ephemeral, Linux-only a možnost swapu.
