# Plantilla para compilar TFGs con LaTeX

Uso Linux, así que la plantilla está pensada alrededor de este sistema operativo.
Si usas Windows, puedes de todas maneras intentarlo a través de WSL

Vas a necesitar:
1. Opcionalmente, instalar Nix, (en este enlace)[https://nixos.org/download/]
1. Copiar la plantilla de TFGs de Matemáticas de la UGR a la carpeta (ugrTFG.cls).
Ya incluye una versión pero puede estar desactualizada.

## Compilar
El archivo raíz es `tfg.tex`.

El proyecto se puede compilar con `nix build` o con el script `./scripts/build.sh`.
Para compilar el PDF de forma continua (eso es, que cada vez que cambias el código LaTeX 
se vuelva a compilar con los cambios), ejecuta `nix develop` o `./scripts/watch.sh`

El TFG y artefactos salen en la carpeta `./build/` o `./result`, con nombre `tfg.pdf`

## Formato
Para ejecutar latexindent y formatear los archivos \*.tex, ejecuta `nix run .#format`,
o el script `./scripts/format.sh`

