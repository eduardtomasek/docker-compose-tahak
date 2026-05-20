# Docker Image Section

## Proč

Původní tahák pokrýval hlavně Docker Compose a nově i Dockerfile, ale chyběl koncepční most mezi:

- tím, co se píše do `Dockerfile`
- tím, co reálně vznikne jako `docker image`
- a tím, co se pak spouští jako container

Sekce `Docker image` doplňuje právě tento mentální model:

- vrstvy
- immutable image
- writable container layer
- union / overlay přístup
- přenos image bez registry
- běžná práce s image v CLI

## Co obsahuje

- Infografiku vrstvení image a container writable layer
- Vysvětlení immutable layers, diff vrstev a copy-on-write
- Rozdíl mezi image a containerem
- Praktickou práci s image:
  - pull
  - build
  - tag
  - run
  - inspect
  - history
  - prune
- Uložení a distribuci image:
  - lokální image store
  - registry
  - `docker image save` / `docker image load`
  - `export` / `import`
  - `commit`

## Zdroje

- Docker Docs: image layers, image basics, storage drivers, containerd image store, `docker image save`, `docker image load`
- OneUptime: union filesystem / overlay2 vysvětlení
- Spacelift: image layers, cache a optimalizace vrstev

## Poznámky k obsahu

- Sekce se drží zavedeného single-file stylu produktu.
- Používá existující UI patterny `tip`, `grid`, `card`, `entry`, `pre.code`.
- Infografika je záměrně textová, aby zůstala lehká, čitelná a konzistentní se zbytkem taháku.
