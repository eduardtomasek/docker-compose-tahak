# Networking v Dockeru — plán

## Cíl

Doplnit sekci vysvětlující, jak Docker řeší komunikaci containerů, publikaci portů a základní network drivery.

## Co má sekce pokrýt

- bridge network a proč je default
- user-defined bridge vs default bridge
- `host` network
- `none` network
- overlay network a kdy dává smysl
- `EXPOSE` vs `-p` / `--publish`
- host-to-container a container-to-container komunikace
- publikace na všechny interfaces vs `127.0.0.1`

## Navržená struktura v taháku

1. Základní mentální model
2. Network drivery
3. Port publishing a `EXPOSE`
4. DNS a komunikace mezi containery
5. Praktické příklady
6. Bezpečnostní poznámky

## Primární zdroje

- Docker Docs — Networking overview  
  https://docs.docker.com/network
- Docker Docs — Bridge network driver  
  https://docs.docker.com/engine/network/drivers/bridge/
- Docker Docs — Host network driver  
  https://docs.docker.com/engine/network/drivers/host/
- Docker Docs — None network driver  
  https://docs.docker.com/engine/network/drivers/none/
- Docker Docs — Overlay network driver  
  https://docs.docker.com/engine/network/drivers/overlay/
- Docker Docs — Publishing and exposing ports  
  https://docs.docker.com/get-started/docker-concepts/running-containers/publishing-ports/
- Docker Docs — Port publishing and mapping  
  https://docs.docker.com/engine/network/port-publishing/
- Docker Docs — docker network connect  
  https://docs.docker.com/reference/cli/docker/network/connect/

## Poznámky k implementaci

- Neplést Compose `ports` syntaxi s obecnou networking teorií.
- U overlay výslovně uvést swarm requirement.
